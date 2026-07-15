# Personal website

Personal website of Boris Knyazhevsky, built as a place to introduce myself and share what I am currently learning and building.

## Stack

- Vue 3
- TypeScript
- SCSS
- Vite
- Docker
- Nginx

## Local development

```sh
npm ci
npm run dev
```

## Production build

```sh
npm run build
```

## Docker

```sh
docker compose up --build -d
```

The container serves the production build at `http://localhost:3000`.

## Checks

```sh
npm run lint
npm run type-check
```
