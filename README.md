<div align="center">
<img height="180" alt="Poku's Logo" src="https://raw.githubusercontent.com/wellwelwel/poku/main/.github/assets/readme/poku.svg">

# @poku/docker

Enjoying **Poku**? [Give him a star to show your support](https://github.com/wellwelwel/poku) 🌟

---

📘 [**Documentation**](https://poku.io/docs/documentation/helpers/containers)

</div>

---

🐳 **@poku/docker** is a minimal API to assist tests that require containers or tests that run inside containers.

> [!TIP]
>
> It can be used both with or without [**Poku**](https://github.com/wellwelwel/poku) test runner.

---

## Quickstart

### Install

<table>
<tr>
<td width="225">

```bash
# Node.js
npm i -D @pokujs/docker
```

</td>
<td width="225">

```bash
# Bun
bun add -d @pokujs/docker
```

</td>
<td width="225">

```bash
# Deno (optional)
deno add npm:@pokujs/docker
```

</td>
</tr>
</table>

### Docker Compose

```js
import { docker } from '@pokujs/docker';

const compose = docker.compose();

// Starts the container(s)
await compose.up();

/**
 * Tests come here 🧪
 */

// Stops the container(s)
await compose.down();
```

### Dockerfile

```js
import { docker } from '@pokujs/docker';

const dockerfile = docker.dockerfile({
  containerName: 'container-name',
  tagName: 'image-name',
});

// Builds the image from the Dockerfile
await dockerfile.build();

// Starts the container
await dockerfile.start();

/**
 * Tests come here 🧪
 */

// Stops and removes both the container and image
await dockerfile.remove();
```
