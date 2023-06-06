# Managed Component To Cloudflare Worker 

Managed Component To Cloudflare Worker provides an easy way for using custom Managed Components with Cloudflare Zaraz, by deploying them as a Cloudflare Worker. Deployed Managed Components can be configured as Tools within [Cloudflare Zaraz](https://dash.cloudflare.com/) from the "Add new Tool" page.

## Usage

> 💡 **Prerequisite:** To deploy a new Cloudflare Worker you need to first login with using `npx wrangler login`

### Using `npx`

Your Managed Component should be bundled before trying to deploy it.

`npx managed-component-to-cloudflare-worker /path/to/managed/component.js component-name`

### Cloning this repository

This method gives you more flexibility but requires you to be familiar with `wrangler` and Cloudflare Workers in general.

- Clone this repository
- Copy your Managed Component files to `./src` (it's recommended to create a new directory within `./src` if you're not using an already bundled Managed Component)
- Import your Managed Component in index.ts by replacing the line `import component from './component.js'` with your `import` command
- Edit [wrangler.toml](wrangler.toml) if you need to change the Worker name or if you're using a more complex Worker configuration for your Managed Component. Your Worker name must start with `custom-mc-` for it to appear in the Cloudflare Dashboard.
- Run `npx wrangler publish`
