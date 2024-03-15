
# Phaser Parcel Template

This is a Phaser 3 project template that uses Parcel for bundling. It supports hot-reloading for quick development workflow and includes scripts to generate production-ready builds.


## theArrowGame - Development Setup


### Ports


Front-end Port (1234): 
    The front-end server runs on PORT 1234 by default. If 1234 is not available, Parcel automatically chooses a random port. For development purposes, we'll keep the ports separate.

Back-end Port (3000): 
    The backend is hard-coded to run on port 3000.

Database Port (5432):   
    Prisma uses PORT 5432 to communicate with the database and listens to the Front-end on PORT 3000.

### Getting Started

Follow these steps after cloning the repository:

1. Clone the repository using git clone <repository-url>.
2. Install all required modules with npm install.
3. Install the latest Prisma version with npm i --save-dev prisma@latest.
4. Initialize Prisma with npx prisma init.
5. Set up DATABASE_URL in the .env file.
6. Update the schema.prisma file to reflect your database schema.
7. Run Prisma Migrate with npx prisma migrate dev --name init.
8. Generate Prisma Client with npx prisma generate.9. 
9. Seed the database with npm run seed.
10. Install the latest Prisma Client with npm i @prisma/client@latest.
11. Generate Prisma Client again with npx prisma generate.
12. Start your application with:

    a. npm run dev for front end 
    b. npm run server for back end 

## Additional Parcel/Phaser Instructions: 

### Versions

This template has been updated for:

- [Phaser 3.80.1](https://github.com/phaserjs/phaser)
- [Parcel 2.11.0](https://github.com/parcel-bundler/parcel)

![screenshot](screenshot.png)

## Requirements

[Node.js](https://nodejs.org) is required to install dependencies and run scripts via `npm`.

## Available Commands

| Command | Description |
|---------|-------------|
| `npm install` | Install project dependencies |
| `npm run dev` | Launch a development web server |
| `npm run build` | Create a production build in the `dist` folder |

## Writing Code

After cloning the repo, run `npm install` from your project directory. Then, you can start the local development server by running `npm run dev`.

The local development server runs on `http://localhost:1234` by default. Please see the Parcel documentation if you wish to change this, or add SSL support.

Once the server is running you can edit any of the files in the `src` folder. Parcel will automatically recompile your code and then reload the browser.

## Template Project Structure

We have provided a default project structure to get you started. This is as follows:

- `index.html` - A basic HTML page to contain the game.
- `src` - Contains the game source code.
- `src/main.js` - The main entry point. This contains the game configuration and starts the game.
- `src/scenes/` - The Phaser Scenes are in this folder.
- `public/assets` - Contains the static assets used by the game.

## Handling Assets

Parcel supports loading assets via JavaScript module `import` statements, which is the recommended way to do it for Parcel.

This template provides support for both embedding assets and also loading them from a static folder. To embed an asset, you can import it at the top of the JavaScript file you are using it in:

```js
import logoImg from './assets/logo.png'
```

To load static files such as audio files, videos, etc place them into the `public/assets` folder. Then you can use this path in the Loader calls within Phaser:

```js
preload ()
{
    //  This is an example of an imported bundled image.
    //  Remember to import it at the top of this file
    this.load.image('logo', logoImg);

    //  This is an example of loading a static image
    //  from the public/assets folder:
    this.load.image('background', 'assets/bg.png');
}
```

When you issue the `npm run build` command, all static assets are automatically copied to the `dist/assets` folder. This is done via the `parcel-reporter-static-files-copy` plugin.

## Deploying to Production

After you run the `npm run build` command, your code will be built into a single bundle and saved to the `dist` folder, along with any other assets your project imported, or stored in the public assets folder.

In order to deploy your game, you will need to upload *all* of the contents of the `dist` folder to a public facing web server.

## Customizing the Template

### Parcel

If you want to customize your build, such as adding plugins for loading CSS or fonts, modify the `parcel/.parcel.*` file for cross-project changes. Or, you can create new Parcel configuration files and target them from specific npm tasks defined in `package.json`. Please see the [Parcel documentation](https://parceljs.org) for more information.

## Cache Issues

### Problem Description

When a file is manually moved out of the `public` folder and then placed back into it, Parcel fails to properly reload the file due to cache management issues. This can result in recent changes not being immediately reflected in the browser.

### Possible Solution

Try deleting the `.parcel-cache` folder and restarting the browser with the cache cleared.

## Join the Phaser Community!

We love to see what developers like you create with Phaser! It really motivates us to keep improving. So please join our community and show-off your work 😄

**Visit:** The [Phaser website](https://phaser.io) and follow on [Phaser Twitter](https://twitter.com/phaser_)<br />
**Play:** Some of the amazing games [#madewithphaser](https://twitter.com/search?q=%23madewithphaser&src=typed_query&f=live)<br />
**Learn:** [API Docs](https://newdocs.phaser.io), [Support Forum](https://phaser.discourse.group/) and [StackOverflow](https://stackoverflow.com/questions/tagged/phaser-framework)<br />
**Discord:** Join us on [Discord](https://discord.gg/phaser)<br />
**Code:** 2000+ [Examples](https://labs.phaser.io)<br />
**Read:** The [Phaser World](https://phaser.io/community/newsletter) Newsletter<br />

Created by [Phaser Studio](mailto:support@phaser.io). Powered by coffee, anime, pixels and love.

The Phaser logo and characters are &copy; 2011 - 2024 Phaser Studio Inc.

All rights reserved.


### Resources 


**Visit** [Get Started with Phaser 3: Fast and Painless] (https://blog.ourcade.co/posts/2019/get-started-phaser3-fast-painless/)


**Clone** [template-parcel to set up a modern Javascript workspace capable of running npm ruin dev, and npm build seamlessly] (https://github.com/phaserjs/template-parcel)

*Watch* [00 Phaser JS with ParcelJS + Typescript - To get and understanding of parcel] (https://www.youtube.com/watch?v=0FFv6DFPJAo)

**Watch** [Javascript Game Development With Phaser - Tiles Mnaps & Plugins] (https://www.youtube.com/watch?v=MR2CvWxOEsw)



