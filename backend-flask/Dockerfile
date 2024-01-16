# The FROM instruction specifies the parent image from which you are building.
FROM python:3.10-slim-buster


# working directory of the container
# The starting point for the container where every command will be run
# Create a directory called /backend-flask
WORKDIR /backend-flask
# Now we are in the /backend-flask directory of the container


# Copy the requirements.txt file from the host machine to the container
COPY requirements.txt requirements.txt


# Install the dependencies in the container
# RUN - Execute build commands in the container
RUN pip3 install -r requirements.txt


# Copy the rest of the files from the host machine to the container
# (.) means everything in the current directory
# 1st (.): the path to the files on the host machine (/backend-flask of the host machine)
# 2nd (.): the path to the files on the container (/backend-flask of the container)
COPY . .


# Set the environment variables for the container
# These environment variables will be set inside the container
ENV FLASK_ENV=development


# EXPOSE - Describe which ports your application is listening on inside the container
EXPOSE ${port}


# Run the command after the container is created
# command: python -m flask run --host=0.0.0.0 --port=4567
CMD [ "python", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]



# -------------------------------------------- DOCKER COMMANDS -------------------------------------------- #

# STEP 1: Build the image

# if pwd is AWS-Tutorials/backend-flask:  
# docker build -t backend-flask .

# if pwd is AWS-Tutorials:  
# docker build -t backend-flask ./backend-flask




# STEP 2: Run the container (if you need environment variables, see below)

# docker run -rm -p 4567:4567 -it backend-flask

# -rm: remove the container after it is stopped
# -p: map the port 4567 of the container to the port 4567 of the host machine
# -it: interactive mode: you can see the logs of the container
# -d: run the container in the background (not in the current terminal)
# -e: set environment variables
# backend-flask: the name of the image

# If you need environment variables, you can use the -e flag
# docker run --rm -p 4567:4567 -it -e FRONTEND_URL='*' -e BACKEND_URL='*' backend-flask