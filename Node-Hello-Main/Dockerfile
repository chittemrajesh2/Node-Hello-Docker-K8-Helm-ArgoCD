# Stage 1: Build
FROM node:14 AS build

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

# Stage 2: Run
FROM node:14-alpine

WORKDIR /app
COPY --from=build /app .
EXPOSE 3000

CMD ["node", "app.js"]