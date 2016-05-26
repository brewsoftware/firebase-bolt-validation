# firebase-bolt-validation

Commonly used firebase type validation rules.

# Dependent Project

  - [Gulp Firebase Bolt](https://www.github.com/brewsoftware/gulp-firebase-bolt) - Bolt compiler with module import support.
  - [Validator](https://github.com/chriso/validator.js) - Validation rules stripped for common regular expressions.
  - [Firebase Bolt](https://www.github.com/firebase/bolt) - Bolt Parser implementation.
  - [Firebase Bolt - Monkey Patch](https://www.github.com/brewsoftware/bolt) - Monkey path to test the new compiler syntax with this plugin.
  - [Firebase Security and Modeling Language](https://www.github.com/firebase/bolt/docs/language.md) - Language documentation and syntax
  

# Using the gulp plugin

Firstly you will need the modified gulp compiler as the root firebase compiler doesn't support import statments yet.

    $ npm install gulp-firebase-bold

Secondly just install this module like any npm package

    $ npm install firebase-bolt-validation

and finally make sure you include a reference to the specific module in your file. This only needs to be included once as a global import

    $ import {'firebase-bolt-validation'}
    path /uuid is UUID {
      read() {true}
      write() {auth != null}
    }

which should give the following in your JSON.

     "uuid": {
      ".validate": "newData.isString() && newData.val().matches(/^[0-9A-F]{8}-[0-9A-F]{4}-[0-9A-F]{4}-[0-9A-F]{4}-[0-9A-F]{12}$/i)",
      ".read": "true"
    }

an example usage for validating 

Enjoy. As always comments and suggestions are welcome. I have pulled what I can from the npm "validator" javascript plugin and will look at pulling in some more use cases soon.

Jason Turner
BrewSoftware

