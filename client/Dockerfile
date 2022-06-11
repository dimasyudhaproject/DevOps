FROM node:16.15.0 as node
ARG ENV
ENV ENV=${ENV}
RUN npm i -g yarn
WORKDIR /home
COPY package.json yarn.lock ./
RUN yarn install --immutable --immutable-cache --check-cache
COPY . .
RUN npm run build
CMD if [ "$ENV" = "dev" ]; \
        then yarn dev; \
    else if [ "$ENV" = "sit" ]; \
        then yarn sit; \
    fi

FROM nginx:1.21.6 as nginx
COPY --from=node /home/nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=node /home/build /usr/share/nginx/html
