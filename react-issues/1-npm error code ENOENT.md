## When I try to create react project, I got below error.
```
npx create-react-app azure-ad-github-spa

npm error code ENOENT
npm error syscall lstat
npm error path C:\Users\vmadmin\AppData\Roaming\npm
npm error errno -4058
npm error enoent ENOENT: no such file or directory, lstat 'C:\Users\vmadmin\AppData\Roaming\npm'
npm error enoent This is related to npm not being able to find a file.
npm error enoent
npm error A complete log of this run can be found in: C:\Users\vmadmin\AppData\Local\npm-cache\_logs\2024-08-11T09_00_04_378Z-debug-0.log
```

The error you're encountering (ENOENT: no such file or directory) suggests that npm is trying to access a directory that doesn't exist on your system. This is typically related to missing or incorrectly configured paths.

Here’s a step-by-step guide to resolve the issue:

1. Ensure Node.js and npm are properly installed:

    - Open the command prompt and run:
      ```
      node -v
      npm -v
      ```
    - If you don't see the versions of Node.js and npm, you might need to reinstall them. Download the latest version from [Node.js official website](https://nodejs.org/) and install it.
2. Create the missing directory manually:
    - Navigate to C:\Users\vmadmin\AppData\Roaming\ and create a folder named npm if it doesn't already exist.
3.  Clear npm cache:
    - Run the following command to clear the npm cache: ```npm cache clean --force```
4. Set correct npm permissions:
    - Sometimes, npm doesn’t have the correct permissions to access certain directories. You can try setting the correct permissions or run the following command to set npm to use a different directory:
      ``` npm config set cache C:\Users\vmadmin\npm-cache --global```
5. Reinstall create-react-app globally:
```
npm uninstall -g create-react-app
npm install -g create-react-app
```
6. After completing the steps above, try creating your React app again
   
```npx create-react-app azure-ad-github-spa```
