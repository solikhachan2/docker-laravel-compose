# Set up
 
1. Pull the Laravel project into the **`src`** folder:
2. Update the 'mysql.env' file to match the configuration in the Laravel project's '.env' file.
3. Ensure that the PHP Docker version specified in 'php.root.dockerfile' matches the PHP version specified in the Laravel project's 'composer.json'
4. If the Laravel root project is located in the 'public' folder, modify the root directory in the 'default.conf' file from '/var/www/html/' to '/var/www/html/public/'."

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

### **Note:** When running `docker-compose`, it will automatically execute `composer install` within the `src` folder.

### **Accessing Services**

- **App:** [http://localhost:8000](http://localhost:8000/)
- **MySQL:**`localhost:3307`**. Use the configured credentials from the **`.env`** file.

## **Stopping Docker Containers**

To stop the Docker containers, run:

```bash

docker-compose down
```
