DOCKER

Network:  test-assignment 
Mongo container name: con-mongo

Cmd :  docker run --network test-assignment --name con-mongo -p 27017:27017 -v data:/data/db --rm -d mongo

Volume backend : mongo

go inside backend folder and execute this command

cmd for building image in backend: docker build -t backend .

backend container name: doc-backend

Cmd for starting backend:  docker run --network test-assignment  --rm -p 80:80 -d -v mongo:/app/logs -v "/Users/harish/Documents/MIS_NEU/Docker_materials/multi-01-starting-setup/backend:/app" -v /app/node_modules --name doc-backend  backend   

go inside frontend folder and execute this command

cmd for building image in frontend: docker build -t frontend .

backend container name: doc-frontend

Cmd for starting frontend:docker run --network test-assignment --name doc-frontend --rm -v "/Users/harish/Documents/MIS_NEU/Docker_materials/multi-01-starting-setup/frontend/src:/app/src“ -p 3000:3000 -d frontend

# Point to remeber

- In comand for front end and backend change the bind mount path to your loacl path to work
- If your changing names of container change the names in the code
- If changing mongodb container name change in backend for running correctly
- Change the image name in docker run if your changing the name while building the image
- If your changing the network name change in other docker command to
- The react docker file use node a base image so no need to do any change for it
  
