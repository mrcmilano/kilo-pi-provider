# kilo-pi-provider

Kilo provider extension for Pi. Access 300+ AI models through the Kilo Gateway.

## Prerequisites

Install [Pi](https://pi.dev) (the coding agent CLI):

```bash
npm install -g @mariozechner/pi-coding-agent
```

## Installation

```bash
pi install git:github.com/mrcmilano/kilo-pi-provider
```

## Usage

Start Pi as usual:

```bash
pi
```

Free models are available immediately. To access all models, log in with your [Kilo](https://kilo.ai) account:

```
/login
```

This opens your browser for device authorization. Once approved, all models become available in the model selector (`Ctrl+L`). Your Kilo credit balance is shown in the footer and refreshes automatically.

You can also set the `KILO_API_KEY` environment variable directly instead of using the login flow. When using an API key, all models and credit balance are loaded at startup without OAuth.

## Security

Model names and IDs are sanitized before terminal rendering to prevent ANSI/control character injection from model metadata. If `KILO_API_URL` is overridden, a warning is printed at startup since all traffic including auth tokens are sent to that endpoint.
