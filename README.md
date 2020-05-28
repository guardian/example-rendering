# Example Rendering

This repo is an opinionated example of how code can be separated out into its own repo, published to Npm, and shared

## The opinions:

ReactJS
Typescript
EmotionJS
MicroBundle
Jest
Storybook
\+ babel, eslint, prettier, husky

## Running locally

This repository is a Github template so you can [create a new one from it](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template). Then

```
yarn
yarn storybook
```

also

```
yarn link // so you don't need to publish to test changes remotely
```

and then

```typescript
    "scripts": {
        "build": "microbundle --jsx React.createElement",
        "dev": "microbundle watch --jsx React.createElement",
        "storybook": "start-storybook -p 6006",
        "build-storybook": "build-storybook",
        "tsc": "tsc",
        "lint": "eslint . --ext .ts",
        "test": "jest --watch"
    }
```

## Publishing

Manual publishing steps:

1. Ensure your changes are on master
2. Ensure you have an [Npm account](https://docs.npmjs.com/creating-and-publishing-scoped-public-packages) that is authorised for the Npm @guardian organisation
3. `yarn build`
4. `yarn publish` (enter new version number, eg. 1.0.1)
5. Then, in the consuming project, update the version of `@guardian/[YOUR_NAME]s` installed to see the changes
