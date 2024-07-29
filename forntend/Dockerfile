# ========= build stage =========
# base image 
FROM node:21 AS frontend-builder

# setup work directory
WORKDIR /app

# copy dependency 
COPY package*.json ./

# install dependency
RUN npm install

# copy the code 
COPY . .

# ========= final stage =========
FROM node:21-slim

WORKDIR /app

COPY --from=frontend-builder /app .

COPY .env .env

EXPOSE 3000

CMD [ "npm", "run", "dev", "--", "--host" ]