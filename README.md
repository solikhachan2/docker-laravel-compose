# Untitled

Created time: December 13, 2023 6:05 PM

## 

```markdown

# Project Docker Setup

This project uses Docker for containerized development. Follow the steps below to set up and run the Docker containers.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed on your machine.

## Getting Started

1. Clone the repository to your local machine:

   ```bash
   git clone <repository-url>

```

1. Navigate to the project directory:
    
    ```bash
    
    cd <project-directory>
    ```
    
2. Pull the Laravel (SIS) project into the **`src`** folder:
    
    ```bash
    
    git clone <laravel-repository-url> src
    
    ```
    
    Replace **`<laravel-repository-url>`** with the URL of your Laravel project repository.
    
3. Create a copy of the **`.env.example`** file in the **`src`** folder and name it **`.env`**. Adjust the environment variables in the **`.env`** file as needed.
    
    ```bash
    
    cp src/.env.example src/.env
    ```
    
    Update the relevant configurations, especially those related to MySQL, if necessary.
    

## **Building and Running Docker Containers**

### **Build Docker Images**

Build the Docker images by running the following command:

```bash

docker-compose build
```

### **Start Docker Containers**

Start the Docker containers using the following command:

```bash

docker-compose up -d
```

The **`-d`** flag runs the containers in the background.

### **Note:** When you run `docker-compose`, it will automatically execute `composer install` within the `src` folder.

### **Accessing Services**

- **App:** Access your Laravel application at [http://localhost:8000](http://localhost:8000/)
- **MySQL:** MySQL is available at **`localhost:3307`**. Use the configured credentials from the **`.env`** file.
- **PHPMyAdmin:** PHPMyAdmin is available at [http://localhost:8080](http://localhost:8080/). Use the configured MySQL credentials.

## **Stopping Docker Containers**

To stop the Docker containers, run:

```bash

docker-compose down
```

This will stop and remove the containers, networks, and volumes defined in your **`docker-compose.yml`** file.

## **Additional Information**

- The project volumes are set up to ensure that changes in the **`src`** directory are reflected in the containers.
- Adjust the Dockerfile configurations in the **`./dockerfiles`** directory if needed.
- Customize the PHP configurations in **`./dockerfiles/php.ini`**.
