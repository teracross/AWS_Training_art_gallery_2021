# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

v0912


# Notes: 
- After trying several versions of ruby, it seems that ruby version 2.7.6 installed via rbenv works.
- Also, remember to install ruby gems, node js (nvm recommended) and yarn (I used Homebrew to do so).
- When running the asset precompile, I ran into the following issue: Compilation failed:
node:internal/crypto/hash:68
  this[kHandle] = new _Hash(algorithm, xofLen);
                  ^

```
Error: error:0308010C:digital envelope routines::unsupported
    at new Hash (node:internal/crypto/hash:68:19)
    at Object.createHash (node:crypto:138:10)
    at module.exports (/Users/edlee/Documents/practice/aws_training/AWS_Training_art_gallery_2021/node_modules/webpack/lib/util/createHash.js:135:53)
    at NormalModule._initBuildHash (/Users/edlee/Documents/practice/aws_training/AWS_Training_art_gallery_2021/node_modules/webpack/lib/NormalModule.js:417:16)
    at /Users/edlee/Documents/practice/aws_training/AWS_Training_art_gallery_2021/node_modules/webpack/lib/NormalModule.js:452:10
    at /Users/edlee/Documents/practice/aws_training/AWS_Training_art_gallery_2021/node_modules/webpack/lib/NormalModule.js:323:13
    at /Users/edlee/Documents/practice/aws_training/AWS_Training_art_gallery_2021/node_modules/loader-runner/lib/LoaderRunner.js:367:11
    at /Users/edlee/Documents/practice/aws_training/AWS_Training_art_gallery_2021/node_modules/loader-runner/lib/LoaderRunner.js:233:18
    at context.callback (/Users/edlee/Documents/practice/aws_training/AWS_Training_art_gallery_2021/node_modules/loader-runner/lib/LoaderRunner.js:111:13)
    at /Users/edlee/Documents/practice/aws_training/AWS_Training_art_gallery_2021/node_modules/babel-loader/lib/index.js:59:103 {
  opensslErrorStack: [ 'error:03000086:digital envelope routines::initialization error' ],
  library: 'digital envelope routines',
  reason: 'unsupported',
  code: 'ERR_OSSL_EVP_UNSUPPORTED'
}

Node.js v20.8.0
```
resolved this by adding the following to the nodeJS environment variables: 
`export NODE_OPTIONS=--openssl-legacy-provider`

- Ran into an issue with the yarn lock file and had to switch registries/ versions for caniuse-lite.