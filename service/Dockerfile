FROM node:16.15.0
WORKDIR /home
COPY package.json .
RUN npm install
COPY . .
CMD ["npm", "start"]