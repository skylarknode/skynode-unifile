# Unifile, unified access to cloud storage services.

[![Build Status](https://travis-ci.org/silexlabs/unifile.png?branch=master)](https://travis-ci.org/silexlabs/unifile) [![Coverage Status](https://coveralls.io/repos/github/silexlabs/unifile/badge.svg?branch=master)](https://coveralls.io/github/silexlabs/unifile?branch=master) [![Known Vulnerabilities](https://snyk.io/test/github/silexlabs/unifile/badge.svg)](https://snyk.io/test/github/silexlabs/unifile) [![bitHound Overall Score](https://www.bithound.io/github/silexlabs/unifile/badges/score.svg)](https://www.bithound.io/github/silexlabs/unifile)

Nodejs library to access cloud storage services with a common API.

[![NPM](https://nodei.co/npm/unifile.png)](https://npmjs.org/package/unifile)

Currently supported services

* FTP
* SFTP
* Dropbox
* GitHub: use git as a cloud with repository and branches as folder
* [RemoteStorage](https://remotestorage.io/)
* WebDAV
* Local filesystem (might be useful to copy from your drive to your cloud)

# Motivation

With the rise of cloud services and the need to be independant of such or such provider, we decided to create a common tool to access a lot of online plateform.

This aim to give the user of your app the liberty of choosing where they want to store their data.


# Use

Requirements

* [Node.js](http://nodejs.org/) > 6.0.0

# Use in your Node.js project

Add unifile lib to your project

```
$ npm install unifile --save
```

## Vanilla Node.js

Unifile use an API similar to the native `fs` module but with Bluebird Promises instead of callbacks.

You can find the whole API documentation on the [project page](https://silexlabs.github.io/unifile/).

## With Express

Then write a small Node.js server [like this one](./samples/simple-api-server.js). Or play with the sample:

```
$ cd samples
$ npm install
$ node simple-api-server.js
```

Then open `http://localhost:6805/` and play with your cloud storages.

## CloudExplorer

You could also take a look at the UI called [CloudExplorer](https://github.com/lexoyo/CloudExplorer2): here's a [live demo](https://cloud-explorer2.herokuapp.com/).

# Privacy

Most of the service in Unifile uses [OAuth 2](http://wiki.oauth.net/w/page/25236487/OAuth%202) to connect the user into the service. This means Unifile doesn't have the user credential at any time.

For the server that doesn't support OAuth, like FTP, the credentials are never stored.

In all case, Unifile never uses any data of the user.

# License

[license: MIT](./LICENSE)

# Developer guide

## Add a service

Unifile works with plugins to connect with more and more services. To find all the plugins available, you can follow the [unifile tag](https://github.com/topics/unifile) on GitHub. Or you can browse this non-exhaustive list:
* [Unifile WebDAV](https://github.com/silexlabs/unifile-webdav)


Unifile is built on modularity, meaning you can create a connector to a service a plug it in Unifile withouth modifying Unifile. So feel free to add any services you need! Don't forget to let us know about it so we could tell everyone :wink:

Here is a list of services which could be useful

* Google Drive
* Amazon S3
* CozyCloud, BTSync
* SkyDrive, RapidShare, CloudMine, FilesAnywhere
* SugarSync
* Facebook (if possibe?)
* a random list of other cloud storage services: Amazon Cloud Drive, Bitcasa, Box, DollyDrive, iCloud Drive, Microsoft OneDrive, SpiderOak, SugarSync, Wuala

## Roadmap

**Let's discuss [this list of issues which set the future of unifile](https://github.com/silexlabs/unifile/labels/enhancement)**

