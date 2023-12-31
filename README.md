# Svelte+Pico

## prerequisites

- [bun](https://bun.sh)

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
bun run dev

# or start the server and open the app in a new browser tab
bun run dev -- --open
```

## Building

To create a production version of your app and run it

```bash
bun run build
cd build
# required environment variables, see: https://github.com/gornostay25/svelte-adapter-bun?tab=readme-ov-file#desktop_computer-environment-variables
export PROTOCOL_HEADER=x-forwarded-proto
export HOST_HEADER=x-forwarded-host
bun run start
```
