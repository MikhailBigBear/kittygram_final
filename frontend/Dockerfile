FROM node:18
WORKDIR /app

COPY package.json package.json
COPY package-lock.json package-lock.json

RUN npm ci

COPY . .
RUN npm install --global server
RUN npm run build

CMD ["npx", "-y", "http-server", "-p", "9000", "/app/build"]
