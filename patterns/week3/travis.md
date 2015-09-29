### continious integration with Travis

#### What is continuous integration?

Continuous integration is a development practice that requires developers to integrate code into a shared repo often. With each pull request is then verified by an automated build tester (ie travis) allowing teams to detect problems as they are created.

#### What is Travis?

Travis CI (continious integration) is a open source hosted continuous integration platform. Once set up and linked to a github repo Travis will build and test your project.

#### How to install Travis for your project

 1. Sign up for Travis using github. Sign up here [here](https://travis-ci.org) and then make sure you authorise the application on github
 ![auth screen](https://cloud.githubusercontent.com/assets/4185328/5859970/3b6fac6a-a256-11e4-9e9a-6b9a38099873.jpg)

 2. On [your Travis profile](https://travis-ci.org/profile) enable the specific github repo you want to test.

 3. create a .travis.yml file in the **root folder** of you repo on your local machine. A .travis.yml file is a basic configuration file that tells Travis CI that our application runs on node and what version of node we want to use.

 4. Taking care to indent `- 0.12`, add the following to your .yml file and save

 ```yml
language: node_js
node_js:
  - 0.12
```

 5. Make sure you have defined your test script in you `package.json` file. So far we have used tape to do this by adding the line `"test": "./node_modules/.bin/tape ./test/*"` inside the script object in `package.json`. i.e. in your script object you must place a test script with the key ``'test'``.
 ![example of test script in `package.json`](https://cloud.githubusercontent.com/assets/2305591/10162353/7d7ba92c-66a2-11e5-8646-2ce250c8a78f.png)

 6. On Travis website navigate to the repo you are using and click on the build status badge next to the name of the repo. copy the text from the markdown tab and paste it into the top of the readme for your repo.

  ![picture of build passing badge](https://raw.githubusercontent.com/dwyl/repo-badges/master/highresPNGs/build-passing.png)

 7. next time you make a pull request Travis will check whether your tests work before you merge.

  ![picture of merging with Travis](https://cloud.githubusercontent.com/assets/2305591/10162420/fa8c4f7a-66a2-11e5-85b9-79e2295f9e3e.png)
