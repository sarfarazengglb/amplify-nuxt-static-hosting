NuxtJs + Amplify + Static hosting for front end

AWS Amplify is a set of tools and services that can be used together or on their own, to help front-end web and mobile developers build scalable full stack applications, 
powered by AWS. You can build frontend within few minutes utilizing AWS infrastructure including CDN(Cloudfront, Route53, etc)

NuxtJS is a swiss army knife for frontend apps.Build your next Vue.js application with confidence using NuxtJS. An open source framework making web development simple and powerful.

Amplify Frontend :-
Use the attached template for building Frontend using Nuxtjs.Edit and update build setting within the frontend setting.


Step 1:Create Nuxt App
yarn create nuxt-app my-nuxt-amplify-app
cd my-nuxt-amplify-app


Step 2:Push to Git
git init
git remote add origin git@github.com:username/my-nuxt-amplify-app.git # or your git repository location
git add .
git commit -m 'initial commit'
git push origin main

Step 3: Login and Setup Amplify frontend and use this git repo

Step 4: In the App build and test settings view, click Edit and do the following:

```
version: 1
frontend:
  phases:
    # IMPORTANT - Please verify your build 
    preBuild:
      commands: 
        - npm install
    build:
      commands: 
        - npm run generate
        - npm run build
  artifacts:
    # IMPORTANT - Please verify your build output directory
    baseDirectory: dist
    files:
      - '**/*'
  cache:
    paths:
     - node_modules/**/*
```

<img src="https://raw.githubusercontent.com/sarfarazengglb/amplify-nuxt-static-hosting/main/App.png">


