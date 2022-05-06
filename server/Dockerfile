FROM node:16.15.0
WORKDIR /home
COPY package.json .
RUN npm install
COPY . .
CMD if [ "$ENV" = "dev" ]; \
        then npm run start:dev; \
    else if [ "$ENV" = "sit" ]; \
        then npm run start:sit; \
    else if [ "$ENV" = "uat" ]; \
        then npm run start:uat; \
    else if [ "$ENV" = "prod" ]; \
        then npm run start:prod; \
    fi
