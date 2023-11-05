# How should you run the applications in this project in Docker?

## _To use the following commands for 1-node-app-ubuntu_
You should first enter the directory:
```
    cd 1-node-app-ubuntu  
```
You should build the Dockerfile:
```sh
    docker build . -t simple-node-app  
```
Run the Dockerfile:
```sh
    docker run simple-node-app 
```

## _To use the following commands for 2-node-app_
You should first enter the directory:
```
    cd 2-node-app  
```
You should build the Dockerfile:
```sh
    docker build . -t simple-node-app-2  
```
Run the Dockerfile:
```sh
    docker run simple-node-app-2
```

## _To use the following commands for 3-node-server_
You should first enter the directory:
```
    cd 3-node-server 
```
You should build the Dockerfile:
```sh
    docker build . -t simple-node-server 
```
Run the Dockerfile:
```sh
    docker run -p 3001:3000 -d simple-node-server
```
Now, when you connect to port 3001 from your computer's browser, you will be able to see the Node server we've set up.

## _To use the following commands for 4-node-mongo-todo_
You should first enter the directory:
```
    cd 4-node-mongo-todo 
```
First, our application needs to connect to a MongoDB server. Therefore, we are initially launching a MongoDB server.
```sh
    docker run --name mongo-server -p 27017:27017 -d mongo 
```

You should build the Dockerfile:
```sh
    docker build . -t custom-todo-app 
```
Run the Dockerfile:
```sh
    docker run --link mongo-server:mongo-alias -p 4000:4000 custom-todo-app
```
We need to send a POST request to the URL http://localhost:4000/todo. The request should include the following Request Body:
>    ```sh
>    {
>        "title": "Title",
>        "description": "Description",
>        "completed": true
>    }
>    ```

After the POST operation we've performed, we can view the data we added by sending a GET request to the URL http://localhost:4000.

## _An example of using entrypoints in 5-cmd-entrypoint_ 
You should first enter the directory:
```
    cd 5-cmd-entrypoint 
```
You should build the Dockerfile:
```sh
    docker build . -t ubuntu-sleeper  
```
In the Dockerfile we've created, there's a default parameter set to 2, so you can run the Dockerfile with or without specifying parameters.
```sh
    docker run ubuntu-sleeper
    //or
    docker run ubuntu-sleeper 10 
```

## _To use the following commands for 6-vue-app-server_
You should first enter the directory:
```
    cd 6-vue-app-server 
```
You should build the Dockerfile:
```sh
    docker build . -t vue-app-server 
```
Run the Dockerfile:
```sh
    docker run -p 9000:8080 -d vue-app-server 
```
Now, when you connect to port 9000 from your computer's browser, you will be able to see the Vue App Server we've set up.

# How To Use Docker Compose

Sometimes, you may need to bring up several services, and for that, you can leverage Docker Compose. 
Let me explain how you can use projects with Docker Compose in these files. 
I'll use an example like a file upload application.

You should first enter the directory:
```
    cd 7-docker-compose/3-file-uploader 
```
After entering the directory, you can bring up the project with the following command:
```sh
    docker-compose up
```
If you want to stop the project, you can do so by running the following command in another console:
```sh
    docker-compose down 
```

This project was made with the help of [Gökhan Kandemir's docker tutorial project](https://github.com/gkandemi/docker) and is a reproduction of [that project](https://github.com/gkandemi/docker).
