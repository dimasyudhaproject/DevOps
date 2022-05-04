FROM node:16 as node
ARG ENV
ENV ENV=${ENV}
WORKDIR /home
COPY package.json .
RUN npm install
COPY . .
CMD if [ "$ENV" = "dev" -o "$ENV" = "sit" ]; \
        then npm start; \
    fi

FROM nginx:1.21.6 as nginx
RUN npm run build
COPY --from=node /home/nginx.conf /etc/nginx/nginx.conf
COPY --from=node /home/build /usr/share/nginx/html