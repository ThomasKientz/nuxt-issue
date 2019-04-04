# Issue

This repo demonstrates a build issue with Nuxt 2.5.1.

`npm run dev` produces :

    WARN  node-fetch@^2.3.0 is required but node-fetch@1.7.3 is installed!
    ERROR  Please install missing dependencies:

    Using yarn:
    yarn add node-fetch@^2.3.0

    Using npm:
    npm i node-fetch@^2.3.0

    FATAL  Missing Template Dependencies

    at Builder.validateTemplate (node_modules/@nuxt/builder/dist/builder.js:5644:13)
    at Builder.build (node_modules/@nuxt/builder/dist/builder.js:5552:12)

This project depends on :
`"firebase": "^5.9.2"`

It appears that Nuxt dependencies are conflicting with one of `firebase`'s dependecy : `node-fetch`.

This issue only happen after a clean reinstall of the dependencies (by deleting `/node_modules` and `package-lock.json` and running `npm i`), so it depends on how `package-lock.json` is constructed.

I am using `npm`.
