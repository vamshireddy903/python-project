# How to Build and Run the Container Manually

# Step 1: Clone the Repository

Open your terminal and run:

    git clone https://github.com/your-username/python-cicd-app.git

Go inside the cloned repo:

    cd python-cicd-app

# Step 2: Build the Docker Image

Since the Dockerfile is inside docker/ and named MyDockerfile, run:

     docker build -t python-app -f docker/MyDockerfile .

**Explanation:**

- -t python-cicd-app → Names the Docker image.  
- -f docker/MyDockerfile → Uses the Dockerfile in the docker/ folder.  
- . → Sets the current folder as the build context so Docker can copy necessary files.

# Step 3: Verify the Image

Check the image exists:

     docker images

# Step 4: Run the Container

    docker run -d -p 5000:5000 --name python-cicd-app python-cicd-app

Explanation:

- -d → Run in detached mode.  
- -p 5000:5000 → Map host port 5000 to container port 5000.  
- --name python-cicd-app → Container name.

# Step 5: Verify the Container

    docker ps

Your container should be running.

# Step 6: Access the Application

Open a browser and go to:

    http://<EC2 Public-ip>:5000

