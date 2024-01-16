FROM node:16.18


# Set the environment variables for the container
ENV PORT=3000


# Copy the rest of the files from the host machine to the container
COPY . /frontend-react-js
# 1st Arg (.) means everything in the current directory of the host machine
# 2nd Arg (/frontend-react-js) means the path to the files on the container


# WORKDIR - The starting point for the container where every command will be run
WORKDIR /frontend-react-js
# Now we are in the /frontend-react-js directory of the container


# RUN - Execute build commands in the container
# Install the dependencies in the container
RUN npm install


# EXPOSE - Describe which ports your application is listening on inside the container
EXPOSE ${PORT}


# CMD - Run the command after the container is created
# command: npm start
CMD ["npm", "start"]