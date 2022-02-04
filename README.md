#### Deprecated in favour of my [create-bd-theme](https://github.com/Gibbu/create-bd-theme) CLI.

- - -

<br>
<br>

# BDThemeTemplate
Quick template to create BetterDiscord themes using SCSS.

## Usage
1. Have [NodeJS](https://nodejs.org/en/) installed.
2. Open a command prompt/terminal and use the following commands:
	1. `npm i -g degit`
	2. `npx degit Gibbu/BDThemeTemplate <your project name>`
		- Example: `cd desktop && npx degit Gibbu/BDThemeTemplate CoolTheme`
	3. `cd <your project name>`
	4. `npm i`
3. Open `scripts/config.json` and change the `name` field to whatever your theme is called.
	- This will tell the other scripts what to output and log.
4. Open `src/_theme.scss` and change the meta fields to fit your needs.
	- You can view all available meta fields [HERE](https://github.com/BetterDiscord/BetterDiscord/wiki/Plugin-and-Theme-METAs).
5. Do the same with `dist/THEME.theme.css`.
	- Change the file name as well as this is what end users will be downloading to use your theme.
6. Open `dist/THEME.theme.css` and change the `@import url` to match your location.
	- Example: `@import url('https://discordstyles.github.io/SoftX/SoftX.css')`
	- `discordstyles` being the username, `SoftX` being the repo and `SoftX.css` being the file.

- - -

#### Development
You should be good to go. Now all you need to do is run the following command: `npm run dev`.  
And it will watch for any changes inside the `src` folder and auto compile them to your BetterDiscord themes folder.

- - -

#### Deployment
If you're wishing to publish your theme for others to use, there's one more step to do.

- Enable GitHub pages on your GitHub repository and set `deploy` as the target.

Now all you need to do is push your changes to the `main` branch and GitHub actions will auto compile your `src` folder to the `deploy` branch.

- - -

#### `scripts/config.json`

This file *should* contain everything you need to personalise the compiler.  

| Property | Type | Description |
| --- | --- | --- |
| `compiler.prefix` | boolean | Run the CSS through the PostCSS autoprefixer. |
| `dev.target` | array | The target of the dev script to watch and autocompile. |
| `dev.output` | array | The path to which your file will compile to. Keeping this to "[ThemeName].theme.css" will usually be fine. |
| `build.target` | array | Much like `dev.target`, but will compile the `_base.scss` to not include the theme end users will download. Note: The last index of the array MUST be a file (ending with a file extension). |
| `build.output` | array | Again, much like `dev.output` but will compile to the local `dist` folder. Note: The compiler will auto create directories if not found.
