# testcafe-browser-provider-selenium
[![Build Status](https://travis-ci.org/alexschwantes/testcafe-browser-provider-selenium.svg)](https://travis-ci.org/alexschwantes/testcafe-browser-provider-selenium)

This is the **Selenium** browser provider plugin for [TestCafe](http://devexpress.github.io/testcafe).

## Install

```
npm install testcafe-browser-provider-selenium
```

## Prerequisites

A Selenium Server up and running, either as standalone or in a grid. Check out the Selenium's [Docker images](https://github.com/SeleniumHQ/docker-selenium) for an easy way to get started with setting up a grid.

## Usage

If you run tests from the command line, use the browser alias when specifying browsers. The '-c 2' parameter will split the tests up and run them across two browsers concurrently. Omit this if it is not needed.

```
testcafe -c 2 selenium:chrome 'path/to/test/file.js'
```

When you use API, pass the alias to the `browsers()` method:

```js
testCafe
    .createRunner()
    .src('path/to/test/file.js')
    .browsers('selenium:chrome')
    .concurrency(2)
    .run();
```

### Specifying the Browser Version and Platform
The browser version and platform can be specified along with the browser name alias in the format:
```
selenium:browserName[@version][:platform]
```
for example:
* selenium:chrome
* selenium:chrome@52.0
* selenium:chrome@52.0:linux

## Configuration

Use the following optional environment variable to set additional configuration options:

 - `SELENIUM_SERVER` - (optional) the url to the selenium server. If not set the default 'http://localhost:4444/wd/hub' will be used.
 
## Author
Alex Schwantes 
