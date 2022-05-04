FROM node:16
WORKDIR /home
COPY package.json .
RUN npm ci
COPY . .
CMD ["npm", "start"]