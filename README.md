# ChatGPT Web Search for OpenCode V2

Configuration and setup notes for the third-party `opencode-chatgpt-websearch` plugin.

## Install globally

```sh
opencode plugin add opencode-chatgpt-websearch@0.1.1
opencode plugin list
```

Restart OpenCode after installation. This installs the pinned npm package in the user's OpenCode configuration; it does not copy the plugin implementation into this repository.

## Use this repository as a project config

The included `opencode.json` pins the plugin for projects opened from this repository. OpenCode V2 installs configured npm plugins when loading the configuration.

## Authentication

The plugin requires an OpenAI integration authenticated with ChatGPT OAuth (browser or headless flow). An OpenAI API key alone is not sufficient. In OpenCode, use `/connect` and complete the available ChatGPT OAuth flow.

On the first web search, select **ChatGPT (experimental)** as the provider. The plugin uses the OAuth access token to call ChatGPT's web-search endpoint. Do not commit OAuth credentials or API keys.

## Check the setup

```sh
opencode plugin list
opencode api get /api/websearch/provider
```

The plugin should appear in the plugin list, and the provider list should include `chatgpt` / **ChatGPT (experimental)**.

## Package

- npm: [`opencode-chatgpt-websearch`](https://www.npmjs.com/package/opencode-chatgpt-websearch)
- Version pinned here: `0.1.1`
- Upstream source: <https://github.com/neriousy/opencode-chatgpt-websearch>
- The plugin and its API are experimental; review upstream changes before updating the pin.
