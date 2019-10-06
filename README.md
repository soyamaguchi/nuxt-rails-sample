# Nuxt(SSR) + Rails API on Docker

### Sample code with separation frontend and backend.

***DEMO:***

![Demo](https://raw.githubusercontent.com/wiki/soyamaguchi/nuxt-rails-sample/imgs/nuxt-rails-sample.gif)

## :pushpin: Installation

Please clone the repository.

```sh
$ mkdir workspace
$ cd workspace
$ git clone git@github.com:soyamaguchi/nuxt-rails-sample.git
```

## :rocket: Environment Building

Build the docker file and create an image.

Then install the package.

```sh
$ cd nuxt-rails-sample
$ docker-compose build
$ docker-compose run --rm frontend yarn install
```

Next, create DB, table, and data.

Finally, create a container and start it.

```sh
$ docker-compose exec backend bash -c 'rails db:create && rails db:migrate && rails db:seed'
$ docker-compose up
```

## :squirrel: Author

[@\_soyamaguchi_](https://twitter.com/_soyamaguchi_)

## :books: Reference

- [How to separate frontend + backend with Rails API, Nuxt.js and Devise-JWT](https://medium.com/@fishpercolator/how-to-separate-frontend-backend-with-rails-api-nuxt-js-and-devise-jwt-cf7dd9da9d16)
- [ReactJS + Ruby on Rails API + Heroku App](https://medium.com/@bruno_boehm/reactjs-ruby-on-rails-api-heroku-app-2645c93f0814)

