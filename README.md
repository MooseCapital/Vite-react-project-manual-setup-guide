
# vite react setup guide

1) In webstorm -> file -> new project -> **vite -> make sure to click React vite then name project.**


    >we must create the project locally because
    >webstorm handles configs simply. Rather than us cloning an empty github config and installing vite-react ourself. 


2) Go to Version control at bottom -> **create repository, this creates local repo only**
    
    when we go to commit & push for the first time, here we define remote branch. If we use the ssh 
   link on Github, then we will not have to retype password when we run 
`Npm run deploy` in the future.


3) Add all our files to git except the configs

    check .gitignore file so it includes package.json, package-lock.json and vite.config.js


4) make sure to install npm when asked -> go into package.json -> in the scripts section add the code

    `"deploy": "gh-pages -d dist"`


5) go to vite.config.js -> after plugins, write base with the current directory on Github

    ` base: "/github project directory"`


6) go to src -> App.css -> delete everything

    >we will be putting all our css for the app in App.css, we start with a clean slate

7) go to Index.css -> and delete everything -> copy the Index.css from here to our new project for nice working defaults we like.


8) copy the **Rubik variable font ttf** file from the public folder here, to our current projects public folder


9) Install gh-pages that lets us easily deploy to gh-pages branch
    
   `npm install gh-pages --save-dev`


10) **Link Images**: When we want to link images, we get errors due to building in the Public Directory files 

    to link properly we must store all images in the **Public** folder. If we hotlink , there is no local storage.

      ```const viteLogo = new URL('/vite.svg', import.meta.url).href```


     or the standard way, may give some warning
   

       ```import viteLogo from '/vite.svg'```
   
   
11) When we want to save, we simply commit and push to the main branch. When we want to build to 
    Github pages we must do this.

```npm run build```
    
```npm run preview```
    
```npm run deploy```
