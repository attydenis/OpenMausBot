# Installing OpenMausBot OSS

This repository preserves the complete redistributable OpenMausBot open-source edition from upstream commit `87d8a797daffb71b125809dcb6b147d31d69262f` (upstream release `v0.1.176`).

The upstream `enterprise/` directory is intentionally excluded because its separate license prohibits redistribution. The remaining application is the ordinary open-source edition under Apache License 2.0.

## Recommended Windows installation

For ordinary use on Windows 11 x64, install the official upstream release rather than compiling this source snapshot:

1. Open the upstream OpenMausBot releases page: `https://github.com/milind-soni/OpenMausBot/releases/latest`.
2. Download `OpenMausBot-setup.exe`.
3. Run the installer. It installs for the current user and does not require administrator rights.
4. The Windows installer was not code-signed as of `v0.1.176`. Windows SmartScreen may display **Unknown publisher**. Verify that the download came from the official upstream release before selecting **More info → Run anyway**.
5. Launch OpenMausBot and complete its setup wizard.
6. Install and sign in to at least one supported local agent CLI: Codex, Claude Code, or Grok CLI. OpenMausBot detects supported CLIs automatically.

Do not paste credentials into source files. Use the application's settings and approval interfaces. Optional integrations such as Composio, Boat, ElevenLabs, Fish Audio, and xAI use separate accounts, credentials, and terms.

## Run from a terminal

Requirements:

- Windows, macOS, or Ubuntu 24.04 x64
- Node.js 24 or newer
- npm
- At least one supported agent CLI installed and authenticated

Install and run:

```sh
npm install -g openmausbot
openmausbot
```

Or run without a global installation:

```sh
npx openmausbot
```

Keep the terminal open while the server is running. Press `Ctrl-C` to stop it. Use `openmausbot setup` to reconfigure it later without deleting bots or conversations.

## Build and run this source snapshot

Requirements:

- Git
- Node.js 24 or newer
- pnpm
- At least one supported agent CLI installed and authenticated

Clone and install:

```sh
git clone https://github.com/attydenis/OpenMausBot.git
cd OpenMausBot
pnpm install
```

Start the development components in separate terminals:

```sh
pnpm dev:server
```

```sh
pnpm dev
```

```sh
pnpm dev:desktop
```

The harness listens on `127.0.0.1:8799`, and the web application normally opens at `http://127.0.0.1:5199`.

## Verify the source before packaging

```sh
pnpm typecheck
pnpm test
pnpm build
pnpm check:electron
```

Build a Windows installer and ZIP:

```sh
pnpm package:win
```

The resulting packages are written under the project's release-output directory. Locally generated packages are not included in this repository.

## Security notes

- Review every request before granting computer, shell, file, browser, email, GitHub, or connected-app access.
- Begin with local-only operation and the minimum permissions needed.
- Keep unattended schedules disabled until their actions and approval behavior have been tested.
- Treat imported teams, skills, MCP servers, and community templates as untrusted until reviewed.
- Do not reuse credentials belonging to another agent, computer, user, or profile.
- The terminal/server setup may store some keys in local configuration. The packaged desktop application provides stronger operating-system-backed storage for supported credentials, but some engine and MCP values can still remain in local configuration. Review upstream credential-storage documentation before connecting sensitive accounts.
- OpenMausBot supports optional anonymous analytics. Review and disable it in **Settings → General → Usage analytics** if desired.

## Upstream documentation

The original `README.md`, `docs/`, `LICENSE`, `NOTICE`, and `LICENSING.md` are preserved in this repository. Consult them for current capabilities, self-hosting, Tailscale, MCP, computer-use, mobile-pairing, and provider instructions.
