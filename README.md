### Build the application image using the docker build command:
sudo docker build -t your_dockerhub_username/nodejs-image-demo .

### It will take a minute or two to build the image. Once it is complete, check your images:
sudo docker images

### It is now possible to create a container with this image using docker run, <br />
Run the following command to build the container: <br />
sudo docker run --name nodejs-image-demo -p 80:8080 -d your_dockerhub_username/nodejs-image-demo

### Once your container is up and running, you can inspect a list of your running containers with docker ps: <br />
sudo docker ps

### With your container running, you can now visit your application by navigating your browser to: <br />
http://your_server_ip.

### Using a Repository to Work with Images
sudo docker login -u your_dockerhub_username

### You can now push the application image to Docker Hub using the tag you created earlier, your_dockerhub_username/nodejs-image-demo:
sudo docker push your_dockerhub_username/nodejs-image-demo

### Let’s test the utility of the image registry by destroying our current application container and image and rebuilding them with the image in our repository. <br />
sudo docker ps

### Using the CONTAINER ID listed in your output, stop the running application container. Be sure to replace the highlighted ID below with your own CONTAINER ID: <br />
sudo docker stop CONTAINER ID

### List your all of your images with the -a flag:
sudo docker images -a

### Remove the stopped container and all of the images, including unused or dangling images, with the following command: 
sudo docker system prune -a

### With all of your images and containers deleted, you can now pull the application image from Docker Hub:
sudo docker pull your_dockerhub_username/nodejs-image-demo <br />
sudo docker images

### You can now rebuild your container using the command from Step 3:
sudo docker run --name nodejs-image-demo -p 80:8080 -d your_dockerhub_username/nodejs-image-demo <br />
sudo docker ps
