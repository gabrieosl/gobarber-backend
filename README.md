<p align="center">
  <img src="src/logo.svg" width="200" />
</p>

<h1 align="center">
  GoBarber - Backend
</h1>

<p align="center">A REST API for GoBarber App. </p>

<p align="center">
  <img src="https://img.shields.io/github/last-commit/gabrieosl/gobarber-node?color=067bc2" />
  <img src="https://img.shields.io/github/license/gabrieosl/gobarber-node?color=067bc2" />
  <img src="https://img.shields.io/github/issues/gabrieosl/gobarber-node?color=067bc2" />
  <img src="https://img.shields.io/github/repo-size/gabrieosl/gobarber-node?color=067bc2" />
  <img src="https://img.shields.io/github/languages/top/gabrieosl/gobarber-node?color=067bc2" />
  <img src="https://img.shields.io/codefactor/grade/github/gabrieosl/gobarber-node?color=067bc2" />
  <img src="https://app.buddy.works/gabriel-2/nodejs-gobarber-mvc/pipelines/pipeline/258559/badge.svg?token=4aeafe081fef58c078ccd27dab4baf120271ebcb8592d512f494f0d538c816f0&" />
</p>

<p align="center">
  <a href="#-about">About</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#-technologies">Technologies</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#-run-it-yourself">Run it yourself</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#-deploy-it-yourself">Deploy it yourself</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#-contributing">Contributing</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#-license">License</a>
</p>
<br />

# 👨🏻‍💻 About

This API provides everything needed to manage users, providers, appointments, schedules and resources for GoBarber ecosystem.

- You can find the version 2 using Typescript [here](https://github.com/gabrieosl/gobarber2-node). _(not backwards compatible)_
- You can find this version's web client [here](https://github.com/gabrieosl/gobarber-react).

# 🚀 Technologies

## Infra

- **HTTP**: Express
- **SQL DB**: Postgres
- **NoSQL DB**: Mongo
- **Cache**: Redis

## Architecture

- **MVC**:
  - **Models**: Appointment, File and User;
  - **Controllers**: Appointment, Avalability, File, Notification, Provider, Schedule, Session and User;
- **Auth**: Bearer Token

## Services

- **CI/CD**: [buddy.works](buddy.works)
- **Error monitoring**: [sentry.io](sentry.io)

## Dependencies

- **ORM**: Sequelize
- **Security**: Bcryptjs, Cors, Helmet, rate-limit
- **Queue**: Bee-queue
- **Mail**: Nodemailer, Handlebars

# ⚙️ Run it yourself

## Tools needed

- [Node.js](https://nodejs.org/en/) v12.X
- [Yarn](https://classic.yarnpkg.com/) or [npm](https://www.npmjs.com/)
- [Docker](https://www.docker.com) _(Recommended)_ or Postgres + Mongo + Redis instances
- [Insomnia](https://insomnia.rest) _(Optional)_

### Docker

If you are using docker, create the instances needed as shown below:

```bash
# Create a postgreSQL instance
$ docker run --name gobarber-postgres -e POSTGRES_USER=docker -e POSTGRES_DB=gobarber -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres

# Create a mongoDB instance
$ docker run --name gobarber-mongodb -p 27017:27017 -d -t mongo

# Create a redis instance
$ docker run --name gobarber-redis -p 6379:6379 -d -t redis:alpine
```

## Clone the project and navigate to it

```bash
$ git clone https://github.com/gabrieosl/gobarber-node.git && cd gobarber-node
```

## Follow these steps

```bash
# Install the dependencies
$ yarn

# Copy '.env.example' as '.env' and fill environment variables according to your settings (Sentry DSN can be left on a development enviroment)
$ cp .env.example .env

# Run migrations
$ yarn sequelize db:migrate

# Run th server
$ yarn dev:server
```

If you are using Insomnia, you can simply import `insomnia.json` into it or click the button below.

<p align="center">
  <a href="https://insomnia.rest/run/?label=GoBarber%20API&uri=https%3A%2F%2Fraw.githubusercontent.com%2Fgabrieosl%2Fgobarber-node%2Fmaster%2Finsomnia.json" target="_blank"><img src="https://insomnia.rest/images/run.svg" alt="Run in Insomnia"></a>
</p>

# ✅ Deploy it yourself

```bash
# build it
$ yarn build

# Run this script to copy e-mail templates left behind by sucrase.
$ yarn copy:templates

# Check if .env is properly set for production and you're ready to run any of these below:
$ yarn start:all
$ yarn start:server
$ yarn start:queue
```

# 💻 Contributing

New features can always be added to this repository. If you want to contribute just fork, add or change want you want and submit a Pull request.

# 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

<br />

Made with ❤️ by Gabriel Lima ✌🏻Check my website [gabrieosl.me](https://gabrieosl.me)
