FROM node:20.20.2-alpine3.23 AS builder

WORKDIR /app
COPY package*.json .
COPY *.js .
RUN npm install

FROM node:20.20.2-alpinne3.23
WORKDIR /app
EXPOSE 8080
COPY --from=builder /app /app
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue" 
RUN groupadd -S roboshop && useradd -S roboshop -G roboshop
USER roboshop
CMD ["server.js"]
ENTRYPOINT ["node"]
