# grunt-contrib-sonar

> This was written to bump up the version attribute in sonar property file as part of the CI process. 

## Getting Started
This plugin requires Grunt `~0.4.4`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-vs-sonar --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-vs-sonar');
```

## The "grunt-contrib-sonar" task

### Overview
In your project's Gruntfile, add a section named `sonar` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  sonar: {
        options: {
            mode: 'jenkins' // sonar
        }
    },
});
```

### Usage Examples

```js
grunt.initConfig({
  sonar: {
    options: {
        mode: 'jenkins'; // other option being 'sonar' passing jenkins adds build id to current version number
    }
  },
});
```

Copy the sonar property file at the same level as the Gruntfile and run the following command:


For mode is sonar:

```bash
> grunt sonar:sonar.properties:patch
Running "sonar:sonar.properties:patch" (sonar) task
Updating version in "sonar.properties" for type "patch"
version updated to 0.0.21
```
Since this uses semver you can pass the following options
major, premajor, minor, preminor, patch, prepatch, or prerelease

read: https://github.com/isaacs/node-semver for more information

For mode is jenkins:

```bash
> grunt sonar:sonar.properties:build1234 # where 1234 is the build id, this could come form the jenkins build variable
Running "sonar:sonar.properties:build1234" (sonar) task
Updating version in "sonar.properties" for type "patch"
version updated to 0.0.21+build1234
```

## TODO
- Add better error handling
- Update the tests so that it actually works

