FROM node:12.10

ENV APP_DIR /app/frontend
ENV PATH /app/frontend/node_modules/.bin:$PATH
ENV TZ Asia/Tokyo
ENV HOST 0.0.0.0

# Nuxt App
RUN mkdir -p /app/frontend
WORKDIR $APP_DIR
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
COPY package.json $APP_DIR/package.json
COPY yarn.lock $APP_DIR/yarn.lock
RUN yarn install
COPY . $APP_DIR
