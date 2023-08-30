FROM node:18-alpine as builder
WORKDIR /app
COPY . .
RUN npm install && npm run build

FROM node:18-alpine as final
WORKDIR /app
COPY --from=builder /app/dist .
CMD ["node", "index.js"]
