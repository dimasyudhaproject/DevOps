FROM node:16.15.0 as node
ARG ENV
ENV ENV=${ENV}
WORKDIR /home
COPY package.json .
RUN npm install
COPY . .
CMD if [ "$ENV" = "dev" -o "$ENV" = "sit" ]; \
        then npm start; \
    fi
RUN if [ "$ENV" = "uat" -o "$ENV" = "prod" ]; \
        then npm run build; \
    fi

FROM nginx:1.21.6 as nginx
COPY --from=node /home/nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=node /home/build /usr/share/nginx/html