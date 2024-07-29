# ========= stage 1 =========
# base image 
FROM node:21 AS bakcend-builder

# setup work directory
WORKDIR /app

# copy the code 
COPY . .

# run the app
RUN npm install

# ========= stage 2 =========
FROM node:21-slim

WORKDIR /app

COPY --from=bakcend-builder /app .

COPY .env .env

EXPOSE 8000

CMD [ "npm", "start" ]