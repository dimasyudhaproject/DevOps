FROM node:16.15.0
WORKDIR /home
COPY package.json .
RUN npm install
COPY . .
CMD if [ "$ENV" = "dev" ]; \
        then npm start:dev; \
    else if [ "$ENV" = "sit" ]; \
        then npm start:sit; \
    else if [ "$ENV" = "uat" ]; \
        then npm start:uat; \
    else if [ "$ENV" = "prod" ]; \
        then npm start:prod; \
    fi
