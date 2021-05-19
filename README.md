# NuxtJs + Amplify + Static hosting for front end

## AWS Amplify
It's a set of tools and services that can be used together or on their own, to help front-end web and mobile developers build scalable full stack applications, 
powered by AWS. You can build frontend within few minutes utilizing AWS infrastructure including CDN(Cloudfront, Route53, etc)

## NuxtJS
Its a swiss army knife for frontend apps based on Vue.js(open source framework).

## Amplify Frontend :-
Use the attached amplify.yml configuration for building Frontend using Nuxtjs on Amplify Platform.Edit and update build setting within the frontend setting.Its not mature Platform yet(when i wrote this 18 May 2021)


## Step 1:Create Nuxt App and Test it locally
yarn create nuxt-app my-nuxt-amplify-app\
cd my-nuxt-amplify-app\
yarn build

## Step 2:Push code to Git repo
git init\
git remote add origin git@github.com:username/my-nuxt-amplify-app.git # or your git repository location\
git add .\
git commit -m 'initial commit'\
git push origin main

## Step 3: Create Amplify App in AWS Console.

Login and Setup Amplify frontend and use this git repo

https://aws.amazon.com/amplify/getting-started/?nc=sn&loc=4

<img src="https://raw.githubusercontent.com/sarfarazengglb/amplify-nuxt-static-hosting/main/app_2.PNG">

## Step 3: Setup Frontend App
Connect your repo and create app
https://console.aws.amazon.com/amplify/home?region=us-east-1#/create

## Step 4: In the App build and test settings view, click Edit and do the following:

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


