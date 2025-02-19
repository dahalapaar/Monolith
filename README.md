# Monolith

![Javascript](https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E) ![Typescript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white) ![NestJS](https://img.shields.io/badge/nestjs-E0234E?style=for-the-badge&logo=nestjs&logoColor=white) ![NextJs](https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white) !["React"](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB) !["TailwindCSS"](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=whit) ![ReactQuery](https://img.shields.io/badge/React_Query-FF4154?style=for-the-badge&logo=ReactQuery&logoColor=white) ![Zod](https://img.shields.io/badge/Zod-000000?style=for-the-badge&logo=zod&logoColor=3068B7) ![Postgres](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)

This is a mono repo template for building full-stack applications with [Turborepo](https://turbo.build/repo). It includes a frontend and backend application, shared libraries, and utilities. This template is a great starting point for building full-stack applications with TypeScript. It consists of a Next.js frontend, NestJs backend, shared libraries, and utilities.

## Table of Contents

- [Monolith](#monolith)
  - [Table of Contents](#table-of-contents)
  - [Using this repo](#using-this-repo)
  - [Setup](#setup)
    - [Ports Exposed](#ports-exposed)
    - [Development](#development)
    - [Build](#build)
  - [What's inside?](#whats-inside)
    - [Apps and Packages](#apps-and-packages)
    - [Utilities](#utilities)
  - [Running NestCLI commands](#running-nestcli-commands)
  - [Pirsma Operations](#pirsma-operations)
    - [Creating a migration](#creating-a-migration)
    - [Running a migration](#running-a-migration)
    - [Generating Prisma Client](#generating-prisma-client)
    - [Running Seeds](#running-seeds)
  - [Bruno Setup](#bruno-setup)
  - [Useful Links](#useful-links)

## Using this repo

Create a repository and follow the steps below to use this template project locally.

1. Add template on your existing repo using `git remote add template https://github.com/CodingWithDibesh/monolith.git` command.
2. Fetch the template repo using `git fetch template` command.
3. Merge the template branch to your desired branch using `git merge template/[branch-name]`

For more information follow the [Stack Overflow](https://stackoverflow.com/questions/56577184/github-pull-changes-from-a-template-repository) conversation for more details.

## Setup

Copy the `.env.example` file to `.env` and fill in the necessary environment variables.

```bash
cp .env.example .env
```

To get started, install the dependencies and run following commands:

```bash
yarn 
```

### Ports Exposed

- Frontend: [http://localhost:7000](http://localhost:7000)
- Postgres: [http://localhost:7001](http://localhost:7001)
- Backend: [http://localhost:7002](http://localhost:7002)
- PGAdmin: [http://localhost:7003](http://localhost:7003)
- Storybook: [http://localhost:7004](http://localhost:7004)

### Development

Run the following command:

```bash
yarn dev
```

This will start the frontend, Storybook.

```bash
yarn dev:be
```

This command will initialize the docker container and backend server. Docker container includes Postgres database, PGAdmin and Backend server.

```bash
yarn dev:fe
```

This command will start the frontend server.

```bash
yarn dev:ui
```

This command will start the Storybook server.

### Build

To build all apps and packages, run the following command:

```bash
yarn build
```

This command will build all the packages and apps.

```bash
yarn build:be
```

This command will build the backend application.

```bash
yarn build:fe
```

This command will build the frontend application.

## What's inside?

Monolith includes the following packages/apps:

### Apps and Packages

- `frontend`: a [Next.js](https://nextjs.org/) app
- `backend`: a [NestJs](https://nestjs.com/) app
- `@repo/ui`: a stub React component library for `frontend`
  `@repo/shared`: a stub utils library shared by both `frontend` and `backend` applications
- `@repo/schemas`: a stub library for shared schemas
- `@repo/tailwindcss-config`: a stub [Tailwind CSS](https://tailwindcss.com/) configuration
- `@repo/eslint-config`: `eslint` configurations (includes `eslint-config-next` and `eslint-config-prettier`)
- `@repo/typescript-config`: `tsconfig.json`s used throughout the monorepo

Each package/app is 100% [TypeScript](https://www.typescriptlang.org/).

### Utilities

Monolith has some additional tools already set for you:

- [TypeScript](https://www.typescriptlang.org/) for static type checking
- [ESLint](https://eslint.org/) for code linting
- [Prettier](https://prettier.io) for code formatting

## Running NestCLI commands

To run NestCLI commands, you can use the following command:

```bash
yarn workspace backend nest [nest command]
```

## Pirsma Operations

Here are some useful Prisma operations you can run in the monorepo.

  - [Creating a migration](#creating-a-migration)
  - [Running a migration](#running-a-migration)
  - [Generating Prisma Client](#generating-prisma-client)
  - [Running Seeds](#running-seeds)

### Creating a migration

Make sure you have the necessary environment variables set in the `.env` file, and the database is running.
To create a migration, run the following command:

```bash
yarn workspace backend prisma migrate dev --name [migration name]
```

### Running a migration

To run a migration, run the following command:

```bash
yarn workspace backend prisma migrate deploy
```

### Generating Prisma Client

To generate the Prisma Client, run the following command:

```bash
yarn workspace backend prisma generate
```

### Running Seeds

To seed the database, run the following command:

```bash
yarn workspace backend prisma db seed
```

## Bruno Setup

To setup Bruno click open collections and browse the [bruno_docs](./apps/frontend/bruno_docs) folder and click open. You should see a monolith collection with all the requests.

## Useful Links

Learn more about the power of Turborepo:

- [Tasks](https://turbo.build/repo/docs/core-concepts/monorepos/running-tasks)
- [Caching](https://turbo.build/repo/docs/core-concepts/caching)
- [Remote Caching](https://turbo.build/repo/docs/core-concepts/remote-caching)
- [Filtering](https://turbo.build/repo/docs/core-concepts/monorepos/filtering)
- [Configuration Options](https://turbo.build/repo/docs/reference/configuration)
- [CLI Usage](https://turbo.build/repo/docs/reference/command-line-reference)
