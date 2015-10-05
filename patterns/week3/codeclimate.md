## Code quality control with Code Climate

### What is Code Climate?

Code Climate uses static analysis to track quality of your project's code.

When creating a GPA (out of a maximum of 4), code climate considers 3 things.
 * Complexity
 * Duplication
 * Style

### How to Implement Code Climate GPA score

 1. Sign up on the [Code Climate](https://codeclimate.com/) website with github account.

 2. Authorise Code Climate to access your github account

 3. Go to your dashboard on Code Climate, and click "add open source repo" and follow the onscreen instructions to add your repo to code Climate

 4. Your GPA score will now be calculated for your repo.

 5. To collect your badge:
  * go to your repos settings on code climate
  * click badges on the left hand side
  * copy the markdown text and paste it into your readme.md on github
![screen shot 2015-09-29 at 16 05 00](https://cloud.githubusercontent.com/assets/2305591/10168242/e2e5d6fe-66c3-11e5-86c9-a9a180e54733.png)

### How to Implement Code Climate Code Coverage score (with tape and istanbul) **Will not work with a forked Repo or branches**

 1. follow the steps above needed to get the code climate gpa score

 2. setup istanbul in your local root.
  * create your tests using tape (as per week3, day one and two)
  * `npm install istanbul --save-dev`
  * add this script to your package.json: `"coverage": "istanbul cover ./node_modules/.bin/tape ./test/*"`
  * run it with `npm run coverage`

 3. you should now have two scripts defined in your `package.json`
  * to run your tests with tape: `"test": "./node_modules/.bin/tape ./test/*",`
  * to get a code coverage with istanbul: ` "coverage": "istanbul cover ./node_modules/.bin/tape ./test/*"`. Note that istanbul is invoking the same script as you test script using tape (but checking that scripts coverage). Your could probably use a different test script with istanbul
![screen shot 2015-09-29 at 16 08 11](https://cloud.githubusercontent.com/assets/2305591/10168358/5422fd6a-66c4-11e5-82c8-1ddbcb18d0ab.png)

 4. If you have not already, generate a coverage report by running npm run coverage (`coverage` is the name of the script defined in `package.json`). You may want to also include the file coverage created by istanbul in your gitignore

 5. You are now ready to send your coverage report to codeclimate.com.
  * navigate to your repo on the climate code website
  * select the settings tab from the nav bar
  * select code coverage on the left and choose JavaScript
  * scroll down and copy the script. it should look like this:
```
"CODECLIMATE_REPO_TOKEN=280d6cac3e8744f75814053b484da641799003d6236e68d2c2bee199951c5132 codeclimate-test-reporter < ./coverage/lcov.info",
```
  * paste this into your scripts in package.json. e.g.
``` json
"codeclimate":"CODECLIMATE_REPO_TOKEN=280d6cac3e8744f75814053b484da641799003d6236e68d2c2bee199951c5132 codeclimate-test-reporter < ./coverage/lcov.info"
```
  * **Note that the token copied here is specific to the repo.**
![screen shot 2015-09-29 at 16 09 08](https://cloud.githubusercontent.com/assets/2305591/10168398/76a282ca-66c4-11e5-8d4f-a16d02bda4ee.png)

  * **note here we have changed the path of `lcov.info` to reflect our file structure**
  * run `npm install codeclimate-test-reporter --save-dev` in you root folder to install and add the reporter to your dependancies.
  * `npm run codeclimate`

 6. Go to code climate and get your badge!

### CODECOV **will work with Forked Repos and Branches**

#### What is Codecov?

 * Another way to check Test coverage but unlike Code Climate, this will work with your branches and forked repos.

 #### How to Implement Codecov

 * Sign up to [Codecov](www.codecov.io) using your github account and authorise access to your repos
 * Simply add the following lines to your `.travis.yml` file (**which you should have if you have set up travis**):
```
before_install:
- pip install --user codecov
after_success:
- codecov --file coverage/lcov.info --disable search
```
 * Remember this will not work if you do not have istanbul installed
 * Make a PR (pull request) and the code coverage will now run and can be accessed via the codecov site - `www.codecov.io/github/YOURUSERNAME/REPONAME`
 * Add the badges for your codecov to the readme.md by selecting the setting icon in the above url and selecting the 'Badge' option
