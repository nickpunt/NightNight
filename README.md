# NightNight
**NightNight** is a set of themes and a theme creation tool for popular web apps. Just copy the stylesheets from NightNight into your favorite stylesheet overriding extension and all your web apps will have a similar appearance.

I created this because I got tired of having to stare at searing white backgrounds at night while working on some of my favorite web apps. Since dark mode was added to MacOS Mojave, there's been a mismatch between the dark mode enabled native apps on MacOS and web apps that do not support color schemes.

NightNight includes a default dark mode theme for popular web apps, and a set of variables you can tweak to create your own theme. You only have to tweak colors once to change the theme stylesheets for all your web apps.

*NOTE: Web Apps frequently tweak their layouts, which inevitably break any CSS overrides like the ones in this tool. If you notice any places where these break, please submit a pull request.*

## Install Browser Extension
A browser extension is required to use NightNight themes. I use [Stylebot](https://chrome.google.com/webstore/detail/stylebot/oiaejidbmkiecgbjeifoejpgmdaleoha) (Chrome), but there are others.

*Be careful about installing browser extensions, as some are shady. Read the reviews!*

## How to Use Default Theme
Every extension that overrides stylesheets works a bit differently. However the basics are as follows:

1. Go to the web app where you want the theme changed (e.g. `https://docs.google.com`).
2. Open the `/css/default` theme folder and find the css file for the app you are on (e.g. `gdocs.css`) and copy contents.
3. Open the extension, paste contents in, and save.
4. Repeat for all the web apps you want to modify.

You're all set!

## How to Create Your Own Theme (optional)
If you want to experiment with creating your own theme, you'll need to set up a few more things. A working knowledge of CSS/SASS and terminal is helpful.

*(Setting up sass is required because browser extensions only support raw css,
  and often do not support css variables.)*

### Sass Setup
First, install [sass](https://sass-lang.com/install).

From the `NightNight` directory in terminal, type:
`npm install -g sass`. You may need to use `sudo`.

Once that installs, close and re-open your terminal window.

### Theme Setup
The default theme has been duplicated into the folder `/sass/mytheme`. You may
change the name of this folder to whatever you like - just be mindful of changing
any instances of `mytheme` in the instructions below. From your theme folder, you
can tweak colors in the file `_colors.scss`.

For your changes to work, you'll need to have sass watch your stylesheets. Just type:
`sass --watch sass/mytheme:css/mytheme`

Now you can edit files in the `/sass/mytheme` folder, and when you save them,
they will compile into `.css` files in the `/css/mytheme` folder

Once you've made some changes, just go into your `/css/mytheme` folder and follow
the instructions above to copy your changes into your browser extension.

To learn more, see the [Sass guide](https://sass-lang.com/guide).

## Requirements
Any browser extension that overrides stylesheets. Chrome and Firefox support this type of extensions, however I don't believe Safari does.

## Supported Web Apps
* [Google Docs](https://docs.google.com)
* [Coda](https://coda.io)
* *more to come*

## Notes
As mentioned above, overriding stylesheets is tricky since web apps often change their styles. Expect themes to not work perfectly! Pull Requests are welcome.

The hope is that web apps will eventually get around to adding their own dark mode theme. If/when that happens, this tool is no longer really useful except if you want to have finer control over their colors. Once web apps like GSuite, Coda, and Airtable add dark mode, I'll stop maintaining this repo.

## Issues
* Google Docs: Icons are unfortunately rather dark, due to PNG colors
* Google Docs: Non-default font colors likely won't work
* Google Docs: Font colors do not work in menus
