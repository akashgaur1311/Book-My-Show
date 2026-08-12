FROM node:26

WORKDIR /app

COPY package.json package-lock.json ./

RUN npm ci --legacy-peer-deps

COPY . .

EXPOSE 3000

ENV PORT=3000
ENV NODE_OPTIONS=--openssl-legacy-provider

CMD ["npm", "start"]
