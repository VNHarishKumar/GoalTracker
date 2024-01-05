DOCKER

Network:  test-assignment 
Mongo container name: mongo

Cmd :  docker run --network test-assignment --name con-mongo -p 27017:27017 -v data:/data/db --rm -d mongo

Volume backend : mongo

Cmd for starting backend:  docker run --network test-assignment  --rm -p 80:80 -d -v mongo:/app/logs -v "/Users/harish/Documents/MIS_NEU/Docker_materials/multi-01-starting-setup/backend:/app" -v /app/node_modules --name doc-backend  backend   


Change script in package.json to run nodemon and add dependencies


Cmd for starting frontend:docker run --network test-assignment --name doc-frontend --rm -v "/Users/harish/Documents/MIS_NEU/Docker_materials/multi-01-starting-setup/frontend/src:/app/src“ -p 3000:3000 -d frontend