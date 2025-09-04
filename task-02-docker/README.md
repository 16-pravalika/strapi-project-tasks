# Task 2 - Dockerize Strapi

## Objective
Containerize the Strapi application using Docker and run it locally.

---

## Steps I Followed

1. **Moved Dockerfile inside Strapi project**
   - Placed `Dockerfile` and `.dockerignore` in `task-01-strapi-local/my-project`.

2. **Created Dockerfile**
   ```dockerfile
   FROM node:18-alpine
   WORKDIR /app
   COPY package*.json ./
   RUN npm install
   COPY . .
   EXPOSE 1337
   CMD ["npm", "run", "develop"]

3. **Created .dockerignore**
    node_modules
    build
    .cache
    Dockerfile
    .dockerignore

4. **Built the Docker image**
    docker build -t strapi-app .

5. **Run the container**
    docker run -it -p 1337:1337 strapi-app

6. **Accessed Strapi Admin Panel**
    Open browser: http://localhost:1337/admin