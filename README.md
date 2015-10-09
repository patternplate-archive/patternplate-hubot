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
Deployment of hubot is easy-as-pie. Just hit the heroku button and you should be good to go. Remember to set the appropriate environment variables for your configuration:
```bash
HUBOT_GITTER2_TOKEN=**** # your gitter access token
HUBOT_GITTER2_IGNORE_ROOMS=**** # rooms for patternplate-hubot to ignore
```

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
