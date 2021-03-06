# Project Setup Checklist
Here's a Rails/React/Redux setup checklist. It should only serve as a reminder.
Ask a TA if you don't understand _why_ you're configuring something on this
list.

* [ ] `rails new`
  * Add `--database=postgresql` if using Postgres.
  * Add `--skip-turbolinks` to skip the turbolinks gem.
* [ ] Update your `Gemfile`.
  * `better_errors`
  * `binding_of_caller`
  * `pry-rails`
  * `annotate`
  * `jquery-rails` (When using rails 5.1+)
* [ ] `bundle install`
* [ ] When using Rails 5.1+, update your `application.js` manifest to include:
  * `//= require jquery`
  * `//= require jquery_ujs`
* [ ] `git init`
  * Update your `.gitignore`.
    * `node_modules/`
    * `bundle.js`
    * `bundle.js.map`
* [ ] `git remote add` the proper remote.
  * `git push -u` the remote.
* [ ] `npm init --yes` to create a package.json file with the default setup.
* [ ] Create a frontend folder at the root of your project with an entry file inside of it.
* [ ] `npm install --save`
  * `webpack`
  * `react`
  * `react-dom`
  * `react-router-dom`
  * `redux`
  * `redux-logger`
  * `redux-thunk`
  * `react-redux`
  * `babel-core`
  * `babel-loader`
  * `babel-preset-react`
  * `babel-preset-es2015`
  * `lodash` (optional)
* [ ] Create a `webpack.config.js` file.
  * The entry point should be in frontend, e.g. `entry: 'frontend/index.jsx'`.
  * The output path should be `'app/assets/javascripts'`.
  * Configure your `module.loaders` to use Babel transpilation for:
    * JSX
    * ES6
  * Include `devtool: 'source-map'`.
* [ ] `git commit` again (Verify that your `.gitignore` works).
  * `git push` your skeleton.

# Front-End Auth Checklist

### Rails Backend

* Set up a `StaticPagesController` with a `root` view containing a
`<main id="root"></main>`.
* Update your `routes.rb` file to root to `static_pages#root`

### Frontend Structure

* Create a `/frontend` folder at the root directory of your project to hold your JavaScript files:

  ```
  frontend
    + actions
    + components
    + reducers
    + store
    + util
    bench_bnb.jsx
  ```

* Run `npm init -y`.
* Run `npm install --save` the following packages:
  * `webpack`
  * `react`
  * `react-dom`
  * `react-redux`
  * `redux`
  * `redux-logger`
  * `babel-core`
  * `babel-loader`
  * `babel-preset-react`
  * `babel-preset-es2015`
* Create a `webpack.config.js` file.
* Set up your entry file (`bench_bnb.jsx`) to render your app into the `#root` container.

Your entry file might start off looking like the code below:
```js
// frontend/bench_bnb.jsx

import React from 'react';
import ReactDOM from 'react-dom';

document.addEventListener('DOMContentLoaded', () => {
  const root = document.getElementById('root');
  ReactDOM.render(<h1>Welcome to BenchBnB</h1>, root);
});
```

* **Test this rendering setup before moving on.**

### Front-End User Auth
