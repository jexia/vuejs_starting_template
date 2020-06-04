FROM node:14.0.0
WORKDIR /app
COPY . .
RUN npm install
ENTRYPOINT npm run build && npm run start