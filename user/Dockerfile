FROM node:20

# this create /app and move there
WORKDIR /app

COPY package.json .
COPY *.js .

RUN npm install
ENV MONGO = "true" \
    MONGO_URL = "mongodb://mongodb:27017/catalogue"
    REDIS_uRL = "redis://redis:6379"

CMD ["node","server.js"]
