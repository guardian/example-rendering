# Example Rendering

There are already several \*-rendering repos designed to isolate areas of code to make sharing easier and maintenence simpler. See [here](https://docs.google.com/document/d/1Z1LPU5_9bqd2hiOTIWuZqkF9Ps-Hfk5qpffPOywR8ys/edit#heading=h.8pvgly6jt73r) for more information on this appraoch.

This repo is an opinionated example of how code can be separated out into its own repo, published to Npm, and shared

## The opinions:

ReactJS
Typescript
EmotionJS
MicroBundle
Jest
Storybook
\+ babel, eslint, prettier, husky

## Usage

To import an atom in your project use `yarn add @guardian/atoms-rendering` then

```
import { TheAtomYouWant } from '@guardian/atoms-rendering';

<TheAtomYouWant someProp={localData.someProp} />
```

## Running locally

```
git clone https://github.com/guardian/atoms-rendering.git
yarn
yarn storybook
```

also

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

### How do you add a new atom to this repo?

Adding a new atom in `atoms-rendering` involves

1. Adding the component, eg. MyComponent.tsx
2. Adding stories, eg. MyComponent.stories.tsx
3. Adding a line to `index.ts` to export the component
4. Publishing a new version of the library to Npm (see below)

## Publishing

Manual publishing steps:

1. Ensure your changes are on master
2. `yarn build`
3. Create a branch, `yourname/v1.0.1`
4. `yarn publish` (enter new version number, eg. 1.0.1)
5. Create a PR for the version
6. Then, in the consuming project, update the version of `@guardian/atoms-rendering` installed to see the changes
