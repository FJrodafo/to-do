## Index

1. [Attribution](#attribution)
2. [Project Structure](#project-structure)
3. [Download the code](#download-the-code)
4. [Using Docker](#using-docker)
5. [Resources](#resources)

## Attribution

This repository is a sample application for users following the getting started guide at https://docs.docker.com/get-started/

The application is based on the application from the getting started tutorial at https://github.com/docker/getting-started

## Project Structure

<details>
<summary>Click me</summary>

```
App/
├── spec/
│   ├── persistence/
│   │   └── sqlite.spec.js
│   └── routes/
│       ├── addItem.spec.js
│       ├── deleteItem.spec.js
│       ├── getItems.spec.js
│       └── updateItem.spec.js
├── src/
│   ├── persistence/
│   │   ├── index.js
│   │   ├── mysql.js
│   │   └── sqlite.js
│   ├── routes/
│   │   ├── addItem.js
│   │   ├── deleteItem.js
│   │   ├── getItems.js
│   │   └── updateItem.js
│   ├── static/
│   │   ├── css/
│   │   │   ├── font-awesome/
│   │   │   │   ├── all.min.css
│   │   │   │   ├── *.eot
│   │   │   │   ├── *.svg#fontawesome
│   │   │   │   ├── *.ttf
│   │   │   │   ├── *.woff
│   │   │   │   └── *.woff2
│   │   │   ├── bootstrap.min.css
│   │   │   └── styles.css
│   │   ├── js/
│   │   │   ├── app.js
│   │   │   ├── babel.min.js
│   │   │   ├── react-bootstrap.js
│   │   │   ├── react-dom.production.min.js
│   │   │   └── react.production.min.js
│   │   └── index.html
│   └── index.js
├── docker-compose.yaml
├── Dockerfile
├── package.json
└── yarn.lock
```
</details>

## Download the code

Open your directory where you save your repositories and clone it with the following command:

```shell
# GitHub
git clone https://github.com/FJrodafo/to-do.git
```

```shell
# GitLab
git clone https://gitlab.com/FJrodafo/to-do.git
```

```shell
# Bitbucket
git clone https://bitbucket.org/fjrodafo/to-do.git
```

## Using Docker

### Run with Docker Compose

Build the container:

```shell
docker compose build
```

Run the container:

```shell
docker compose up -d
```

Stop the Container:

```shell
docker compose down
```

### Build Docker image on your own

If you don't have Node v18 or higher installed on your machine, you can build a Docker image by running the [Dockerfile](./Dockerfile).

Open a terminal and run the following command (Make sure you are in the `App` directory):

```shell
docker build -t to-do .
```

Create a volume by using the `docker volume create` command:

```shell
docker volume create to-do
```

After the build completes, you can run your container with the following command:

```shell
docker run -dp 127.0.0.1:3000:3000 --mount type=volume,src=to-do,target=/etc/todos to-do
```

> [!NOTE]
> 
> After a few seconds, open your web browser to http://localhost:3000

## Resources

To see a more detailed explanation of how this Docker project works, visit the following repository at [GitHub](https://github.com/FJrodafo/University/blob/main/Cheat_sheets/Docker/README.md#overview-of-the-get-started-guide)/[GitLab](https://gitlab.com/FJrodafo/University/-/blob/main/Cheat_sheets/Docker/README.md?ref_type=heads#overview-of-the-get-started-guide).

There is a repository of this same project published on Docker Hub at https://hub.docker.com/r/fjrodafo/to-do

<link rel="stylesheet" href="./README.css">
<a class="scrollup" href="#top">&#x1F53C</a>