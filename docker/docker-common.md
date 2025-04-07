networks:
  common_network:
    driver: bridge

services:
  # MySQL Service
  mysql:
    image: mysql:8.0
    container_name: common_mysql
    restart: unless-stopped
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: common_db
      MYSQL_USER: user
      MYSQL_PASSWORD: password
    ports:
      - "3306:3306"
    volumes:
      - mysql_data:/var/lib/mysql
    networks:
      - common_network

  # phpMyAdmin for MySQL
  phpmyadmin:
    image: phpmyadmin:latest
    container_name: common_phpmyadmin
    restart: unless-stopped
    environment:
      PMA_HOST: mysql
      MYSQL_ROOT_PASSWORD: root
    ports:
      - "8081:80"
    depends_on:
      - mysql
    networks:
      - common_network

  # PostgreSQL Service
  # postgres:
  #   image: postgres:16
  #   container_name: common_postgres
  #   restart: unless-stopped
  #   environment:
  #     POSTGRES_USER: user
  #     POSTGRES_PASSWORD: password
  #     POSTGRES_DB: common_db
  #   ports:
  #     - "5432:5432"
  #   volumes:
  #     - postgres_data:/var/lib/postgresql/data
  #   networks:
  #     - common_network

  # pgAdmin for PostgreSQL
  # pgadmin:
  #   image: dpage/pgadmin4
  #   container_name: common_pgadmin
  #   restart: unless-stopped
  #   environment:
  #     PGADMIN_DEFAULT_EMAIL: admin@example.com
  #     PGADMIN_DEFAULT_PASSWORD: admin
  #   ports:
  #     - "8082:80"
  #   depends_on:
  #     - postgres
  #   networks:
  #     - common_network

  # MongoDB Service
  mongodb:
    image: mongo:6.0
    container_name: common_mongo
    restart: unless-stopped
    ports:
      - "27017:27017"
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: rootpassword
    volumes:
      - mongo_data:/data/db
    networks:
      - common_network
  # Mongo Express for MongoDB (Web UI)
  # mongo_express:
  #   image: mongo-express
  #   container_name: common_mongo_express
  #   restart: unless-stopped
  #   environment:
  #     ME_CONFIG_MONGODB_ADMINUSERNAME: root
  #     ME_CONFIG_MONGODB_ADMINPASSWORD: rootpassword
  #     ME_CONFIG_MONGODB_SERVER: mongodb
  #   ports:
  #     - "8083:8081"
  #   depends_on:
  #     - mongodb
  #   networks:
  #     - common_network

  # Redis Service
  # redis:
  #   image: redis:7
  #   container_name: common_redis
  #   restart: unless-stopped
  #   ports:
  #     - "6379:6379"
  #   networks:
  #     - common_network

volumes:
  mysql_data: # postgres_data:

  mongo_data:
