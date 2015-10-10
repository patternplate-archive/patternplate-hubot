> patternplate's ever-helpful robot

<div align="center">
  <a href="https://github.com/sinnerschrader/patternplate">
    <img width="200" src="https://cdn.rawgit.com/marionebl/patternplate-hubot/master/patternplate-hubot.svg" />
  </a>
</div>
<h1 align="center">:speech_balloon: patternplate-hubot</h1>
<p align="center">
  <b><a href="#about">About</a></b> | <b><a href="#installation">Installation</a></b> | <b><a href="scripts">Scripts</a></b> | <b><a href="deployment">Deployment</a></b> | <b><a href="Development">Development</a></b> | <b><a href="./contributing.md">Contributing</a></b>
</p>
<br />
> Health

[![npm version][npm-image]][npm-url] [![Downloads][npm-dl-image]][npm-url] [![Build status][ci-image]][ci-url]

> Standards

[![Commitizen friendly][commitizen-image]][commitizen-url]  [![Dependency management][dependency-manager-image]][dependency-manager-url] [![Release management][release-manager-image]][release-manager-url]
![Ecmascript version][ecma-image] [![Javascript coding style][codestyle-image]][codestyle-url] [![License][license-image]][license-url]

> Reach out

[![chat with patternplate][gitter-image]][gitter-url]

> Deployment

[![Deploy to Heroku][heroku-image]][heroku-url]

## About
patternplate-hubot is patternplate's ever-helpful robot living in our gitter room. It is a proud descendant of Github's famous hubot and as such, helps with everything a robot could do and some more. Come visit it on [gitter][gitter-url].

## Installation
[patternplate-hubot](npm-url) is available on npm.
```
npm install --save patternplate-hubot
```

## Scripts
Currently patternplate-hubot has the following modules enabled:

* hubot-diagnostics
* hubot-help
* hubot-heroku-keepalive
* hubot-google-images
* hubot-google-translate
* hubot-pugme
* hubot-maps
* hubot-rules
* hubot-shipit

## Deployment
Deployment of hubot is easy-as-pie. You'll be up and running in a few simple steps.

### Heroku setup
The initial setup couldn't be easier.
* [![Deploy to Heroku][heroku-image]][heroku-url]
* In the deployment dialog, choose a **heroku application name** and take note of it
* Done!

### Basic configuration
For patternplate-hubot to work reliably, you'll have to do a bit of configuration.
* Create a new Github user for your patternplate-hubot
* Login to gitter with patternplate-hubot's account
* Join the gitter rooms patternplate-hubot should be active in
* Retrieve the **gitter access token** for patternplate-hubot's account at [developer.gitter.im/apps](https://developer.gitter.im/apps)
* Retrieve the **heroku app web url** by using heroku cli:
```bash
heroku apps:info --shell --app <heroku-app-name> | grep web-url | cut -d= -f2
```
* Set the appropriate environment variables for your patternplate-hubot.
```bash
heroku config:set HUBOT_GITTER2_TOKEN=<gitter-access-token> --app <heroku-app-name>
heroku config:set HUBOT_HEROKU_KEEPALIVE_URL=<heroku-app-web-url> --app <heroku-app-name>
```
* Restart your heroku application
```bash
heroku restart --app <heroku-app-name>
```
* Well done! Your first patternplate-hubot instance is ready for duty. :fist:

### Always on configuration
Heroku's free plan requires your brand new app to sleep at least six hours a day. By default patternplate-hubot will sleep in the hours from 22:00 to 06:00. To provide patternplate-hubot 24/7 you'll want two heroku instances running on the schedule outlined below.

| :clock3: Time          | :sunny: Dayshift      | :crescent_moon:  Nightshift|
|:--------------|:--------------|:--------------|
| 06:00         | :coffee: Wakes up      | :sleepy: Goes to sleep |
| 06:00 - 22:00 | :speech_balloon: On Duty       | :sleeping: Sleeping      |
| 22:00         | :sleepy: Goes to sleep | :coffee: Wakes up      |
| 22:00 - 06:00 | :sleeping: Sleeping      | :speech_balloon: On Duty       |



* Create a second instance following the steps at [Basic configuration](#basic-configuration)
* Choose distinct names for your instances. We used `*-dayshift` and `*-nightshift`
* Configure your nightshift instance to be awake at night:
```bash
heroku config:set HUBOT_HEROKU_WAKEUP_TIME=22:00 --app <heroku-app-name>
heroku config:set HUBOT_HEROKU_SLEEP_TIME=06:00 --app <heroku-app-name>
```
* For **each of your instances** do:
* Create a **scheduler** associated to the instance and open its configuration interface
```bash
# this is free but you'll need a verified heroku account (with credit card information) for this
heroku addons:create scheduler:standard --app <heroku-app-name>
heroku addons:open scheduler --app <heroku-app-name>
```
* Hit `Add a new job`
* Enter the following command into the `$` field
```bash
curl ${HUBOT_HEROKU_KEEPALIVE_URL}heroku/keepalive
```
* Set the next due field to the time when you want this intance to wake up. Typically this is `06:00` for your dayshift and `22:00` for your nightshift instance.
* Boom! patternplate-hubot now is always on duty.

## Development
You dig patternplate-hubot and want to submit a pull request? Awesome!
Be sure to read the [contribution guide](./contributing.md) and you should be good to go.
Here are some notes to get you coding real quick.

Fetch, install and start the default watch task
```
git clone https://github.com/sinnerschrader/patternplate-hubot.git
cd patternplate-hubot
npm install
npm start
```

---
patternplate-hubot is built by SinnerSchrader with :heart: and released under the [MIT License](./license.md).
Robot icon by [Edward Boatman](https://thenounproject.com/edward/).

[npm-url]: https://www.npmjs.org/package/patternplate-hubot
[npm-image]: https://img.shields.io/npm/v/patternplate-hubot.svg?style=flat-square
[npm-dl-image]: http://img.shields.io/npm/dm/patternplate-hubot.svg?style=flat-square

[ci-url]: https://travis-ci.org/marionebl/patternplate-hubot
[ci-image]: https://img.shields.io/travis/marionebl/patternplate-hubot.svg?style=flat-square
[coverage-url]: https://coveralls.io/r/marionebl/patternplate-hubot
[coverage-image]: https://img.shields.io/coveralls/marionebl/patternplate-hubot.svg?style=flat-square
[climate-url]: https://codeclimate.com/github/marionebl/patternplate-hubot
[climate-image]: https://img.shields.io/codeclimate/github/marionebl/patternplate-hubot.svg?style=flat-square

[pr-url]: http://issuestats.com/github/marionebl/patternplate-hubot
[pr-image]: http://issuestats.com/github/marionebl/patternplate-hubot/badge/pr?style=flat-square
[issue-url]: https://github.com/sinnerschrader/patternplate/issues
[issue-image]: http://issuestats.com/github/sinnerschrader/patternplate/badge/issue?style=flat-square

[dependency-manager-image]: https://img.shields.io/badge/tracks%20with-greenkeeper-3989c9.svg?style=flat-square
[dependency-manager-url]: https://github.com/greenkeeperio/greenkeeper
[release-manager-image]: https://img.shields.io/badge/releases%20with-semantic--release-3989c9.svg?style=flat-square
[release-manager-url]: https://github.com/semantic-release/semantic-release
[buildsystem-url]: https://github.com/flyjs/fly
[ecma-image]: https://img.shields.io/badge/babel%20stage-0-3989c9.svg?style=flat-square
[codestyle-url]: https://github.com/sindresorhus/xo
[codestyle-image]: https://img.shields.io/badge/code%20style-xo-3989c9.svg?style=flat-square
[license-url]: ./license.md
[license-image]: https://img.shields.io/badge/license-MIT-3989c9.svg?style=flat-square
[commitizen-url]: http://commitizen.github.io/cz-cli/
[commitizen-image]: https://img.shields.io/badge/commitizen-friendly-3989c9.svg?style=flat-square

[gitter-image]: https://img.shields.io/badge/gitter-join%20chat-3989c9.svg?style=flat-square
[gitter-url]: https://gitter.im/sinnerschrader/patternplate

[patternplate-url]: /sinnerschrader/patternplate

[heroku-image]: https://img.shields.io/badge/deploy%20to-heroku-7059bc.svg?style=flat-square
[heroku-url]: https://heroku.com/deploy?https://github.com/sinnerschrader/patternplate-hubot
