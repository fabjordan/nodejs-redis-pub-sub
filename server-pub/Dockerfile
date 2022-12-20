FROM node:14-alpine as node
WORKDIR /home/app
COPY . .
RUN npm install
EXPOSE 3001
CMD ["npm", "run", "dev"]