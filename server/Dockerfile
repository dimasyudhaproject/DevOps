FROM node:16.15.0
ARG ENV
ENV ENV=${ENV}
WORKDIR /home
COPY package.json yarn.lock ./
RUN yarn install --immutable --immutable-cache --check-cache
COPY . .
CMD if [ "$ENV" = "dev" -o "$ENV" = "sit" ]; \
        then yarn dev; \
    else if [ "$ENV" = "uat" -o "$ENV" = "prod" ]; \
        then yarn prod; \
    fi
