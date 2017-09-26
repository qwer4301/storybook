# Setting up a dev environment

## Prerequisites

Please have the **_latest_** stable versions of the following on your machine

-   node
-   yarn
-   @storybook/cli

## Initial Setup

If you run into trouble here, make sure your node, npm, and **_yarn_** are on the latest versions (yarn at least v1.0.0).

1.  `cd ~` (optional)
2.  `git clone https://github.com/storybooks/storybook.git` _bonus_: use your own fork for this step
3.  `cd storybook`
4.  `yarn`
5.  `yarn bootstrap --core`
6.  `yarn test --core`

### Bootstrapping everything

This method is slow, and if you are reading this tutorial you probably don't want to do it

1.  `yarn bootstrap`
2.  At the prompt: `a`, `enter`, `y`, `enter` ( `a` selects all (fully bootstrap) and `y` is to confirm)
3.  Have a beer 🍺
4.  `yarn test` (to verify everything worked)

## Working with the kitchen sink app

TODO: Fill this in

## Connecting Your App To Storybook

**_Note:_** If you aren't seeing addons after linking storybook, you probably have a versioning issue which can be fixed by simply linking each addon you want to use.

### Linking Storybook

Storybook is broken up into sub-projects that you can install as you need them. For this example we will be working with `@storybook/react`.
**Note:** You need to `yarn link` from inside the sub project you are working on **_NOT_** the storybook root directory

1.  `cd app/react`
2.  `yarn link`

### Setup Storybook In Your Project

#### React

##### 1. Setup storybook in your project

First we are going to install storyboook, then we are going to link `@storybook/react` into our project. This will replace `node_modules/@storybook/react` with a symlink to our local version of storybook. 

1.  `getstorybook`
2.  `yarn storybook`
3.  Verify that storybook works

##### 2. Link

1.  Go to your storybook _root_ directory 
2.  `yarn dev`
3.  Wait for the output to stop 
4.  Go to your storybook-sandbox-app directory
5.  `yarn link @storybook/react`
6.  `yarn storybook`

#### ReactNative

TODO: Fill this in

#### Vue

TODO: Fill this in

### Verify your local version is working

You should now have a working storybook dev environment up and running. To verify this you can make changes to the following file:

`open app/react/src/client/manager/preview.js`

Save and go to `http://localhost:9009` (or wherever storybook is running)

If you don't see the changes rerun `yarn storybook` again in your sandbox app

## Issues

If you had any issues following this tutorial, please don't hesitate to open up a support ticket.

If you have any improvements to this tutorial, please don't hesitate to open up a pull request.

If you still have questions after going throught this tutorial (and you have confirmed that your versions of node, npm and yarn are up to date) come reach out to us on slack at <https://storybooks.slack.com/>