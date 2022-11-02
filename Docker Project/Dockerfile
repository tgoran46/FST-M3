FROM node:alpine as builder
WORKDIR /app
COPY . .
RUN npm install
CMD ["npm", "run", "build"]

# Run Phase
FROM node:alpine
WORKDIR /app
COPY package.json ./
RUN npm install
COPY --from=builder /app/dist .
CMD ["node", "server.js"]