FROM node:8.7-alpine
COPY package.json .
RUN npm install 
RUN mkdir -p /opt/app && cp -a /node_modules /opt/app
COPY index.js .
COPY public/ public/
EXPOSE 8080
CMD ["node","index.js"]

