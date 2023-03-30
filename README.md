# npm-fetch-repos-data-script
NPM script for fetching and syncing data between different repos


``` 
"config": {
    "frontendSSH": "git@gitlab.com...",
    "defaultBranch": "master",
    "sharedFolderPath": "commonConstants"
},
"scripts": {
    "fetchFolderFromRepo": "run(){ branch=${1:-$npm_package_config_defaultBranch} && git archive --remote=$npm_package_config_frontendSSH $branch $npm_package_config_sharedFolderPath/*.js | tar xvf -; }; run",
    "removeFolder": "rimraf $npm_package_config_sharedFolderPath/*.js",
    "getFolder": "npm run removeFolder && npm run fetchFolderFromRepo"
},
```
<img width="457" alt="image" src="https://user-images.githubusercontent.com/54443742/228807077-5a7a44ef-49a3-4156-9002-d952bd9b84bd.png">
