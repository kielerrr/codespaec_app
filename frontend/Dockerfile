FROM node:20-bullseye

WORKDIR /app

COPY package.json ./
COPY package-lock.json ./
RUN npm install

COPY . .

EXPOSE 5173
RUN echo "ABOUT TO RUN NPM RUN"
# Must be present at the end of frontend/Dockerfile
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]
