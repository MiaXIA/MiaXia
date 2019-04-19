This is the source codes for web pages [https://miaxia.github.io/mcx/](https://miaxia.github.io/mcx/).<br>
This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).<br>
Dev branch is used for development, and the published static files are in gh-pages branch

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.<br>
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br>
You will also see any lint errors in the console.

### `npm run deploy`

Deploy this app on github pages [https://miaxia.github.io/mcx/](https://miaxia.github.io/mcx/)

### `npm test`

Launches the test runner in the interactive watch mode.<br>
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.<br>
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br>
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (Webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## How to deploy react app on github pages
I created a react app at my local, then I tried to upload it onto git repository and deploy it with github pages.
### Create a New Empty Repository
Create a new repository, note that avoid the format of `username/github.io` as repository name. Because it will mark this repo as personal pages and the defalut publish branch must be master and you cannot change it.
![image](https://github.com/MiaXIA/mcx/raw/dev/images/createRepo.png)

You don't need readme and gitignore file, click `create repository` and you will have the new repo.

### Upload React App onto Repository
I assume that you have a existed react app at local, then you can use terminal to upload this react app onto the repo you just created.

``` java
cd Desktop/personalBlogReactApp //go to the react app folder
git init //init git
//sometimes it will ask you gihub account and password if you didn't set up, follow the instruction and sign in
git add . //add all files
git commit -m "first commit" //commit to local
git remote add origin https://github.com/MiaXIA/personalBlog.git //the repository address of project
git push -u origin master //push all the files to remote branch
```
Then refresh the github page you can see all the codes are there.

### Setup Deploy Script and Package.json file
You need to install a package called gh-pages
``` java
npm install --save gh-pages
```

Then you need to edit the package.json file in your react app, add the homepage and some deploy scripts.
``` java
"homepage":"https://yourusername.github.io/repository-name"
//Here my homepage address will be https://miaxia.github.io/mcx/
"scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build",
}
```
You are almost done! In your terminal, you need one more line:
``` java
npm run deploy
```

### Settings
After created the new repo and uploaded the react app. Goto the settings on the repo's main page, scroll down and find the `GitHub Pages` title.
Once you successfully deployed, then one last thing you need to do is change the `Source` of `Github Pages` to `gh-pages branch`
![image](https://github.com/MiaXIA/mcx/raw/dev/images/githubPages.png)

Also you can see the notification `Your site is publish at xxx` once you change the source branch.

Enjoy your new react app personal blog!



