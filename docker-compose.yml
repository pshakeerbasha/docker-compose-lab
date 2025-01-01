version: '3.8'

services:
  app:
    image: python:3.9-slim  # You can choose any application image
    container_name: web_app
    command: python -m http.server  # Start a simple HTTP server for demonstration
    ports:
      - "5000:5000"  # Expose port 5000 on the host to port 5000 in the container
    volumes:
      - ./app:/app  # Mount the local directory `./app` to the `/app` directory in the container
    depends_on:
      - db  # Ensure MySQL is started before the app
    environment:
      MYSQL_HOST: db  # Set MySQL service hostname for the app to access MySQL

  db:
    image: mysql:8.0
    container_name: mysql_db
    environment:
      MYSQL_ROOT_PASSWORD: rootpassword  # Set root password for MySQL
      MYSQL_DATABASE: my_database  # Name of the database to be created
    ports:
      - "3306:3306"  # Expose port 3306 on the host to port 3306 in the container
    volumes:
      - mysql-data:/var/lib/mysql  # Persist MySQL data using a named volume

volumes:
  mysql-data:
