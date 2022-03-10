# Known Windows Issues

1. if you are facing issues with "CI" package, or any other issue involving "CI" while trying to run the project ( via "npm start" ), you can try to change line 22 in the file "client/package.json" 
from 
"start": "CI=true react-scripts start",
to 
"start": "set CI=true && react-scripts start",

2. if you're terminal stuck on "starting development server" please replace line 10 at the root package.json file 
from 
"start": "lerna run start --parallel",
to
"startclient": "cd client && npm start",
"startserver": "cd server && npm start",
"start": "npm run startserver | npm run startclient",

3. The type of project that you got, called a "mono-repo," it's in very common use in the industry.
In that type of repos the npm commands like "npm install" and "npm start" needs to be executed in the root folder and not in each subproject separately.
You can read more about that here if you wise to understand it deeply.

4. If for any reason, some ports are already in use, or you are falling terminate the process use those :
windows users - taskkill /f /im node.exe
