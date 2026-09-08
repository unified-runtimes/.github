<picture>
  <source media="(prefers-color-scheme: dark)" srcset="logo-dark.svg">
  <img alt="Unified Runtimes" src="logo.svg" width="420">
</picture>

Open-source serverless compute, in two repos.

[executor](https://github.com/unified-runtimes/executor) runs functions in containers. It is a Rust rewrite of the [OpenRuntimes executor](https://github.com/open-runtimes/executor) that Appwrite uses, with the same HTTP API and the same runtime contract, so you can swap it in without touching the callers. On a 4 vCPU runner it cold starts in about 220 ms, against roughly 650 ms for the PHP one.

[runtimes](https://github.com/unified-runtimes/runtimes) holds the container images those functions run inside. They speak the OpenRuntimes v5 runtime contract and boot through one static Rust init binary rather than shell lifecycle scripts. The first wave is Node, Python, PHP, static, Bun, Deno, Go and Rust, each with the current language version and the three before it.

Images are named `ghcr.io/unified-runtimes/<family>:v5-<version>`, so Node 22 is `ghcr.io/unified-runtimes/node:v5-22`.

Either piece works on its own. The images run under the OpenRuntimes executor, and our executor runs the OpenRuntimes images.

The executor is AGPL-3.0 and the images are MIT. Setup and configuration live in each repository's README.

Found a security problem? Email security@unifiedprojects.co.uk rather than filing a public issue.

<a href="https://unifiedprojects.co.uk">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://unifiedprojects.co.uk/assets/unified-projects-badge-built-by-dark.svg">
    <img alt="Built by Unified Projects" src="https://unifiedprojects.co.uk/assets/unified-projects-badge-built-by-light.svg" height="48">
  </picture>
</a>
