FROM node:{NODE_VERSION}{DOCKER_TYPE} as nodedev 
WORKDIR /app
RUN groupadd -g 61000 ferris 
RUN useradd -g 61000 -l -M -s /bin/false -u 61000 ferris 
RUN mkdir -p /app
USER ferris
COPY package.json package-lock.json .
RUN npm ci
COPY . .
RUN chown -R ferris:ferris /app
EXPOSE 3000




