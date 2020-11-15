# Real_Word_nuxtjs
## Steps

### 1. Scaffold the whole project

#### 1.1 git 

        - 1. Create repo in github
        - 2. git clone the repo to local
        - 3. Test commit and push 

#### 1.2 Install Nuxt.js and init the project
        
        - 1. npm init & npm i nuxt
        - 2. add scripts in package.json
             
             "dev": "nuxt"
        - 3. Create home pages to test if the Nuxt works

when running nuxt command, it will auto-generate the .nuxt folder where includes the compiled project files
#### 1.3 Import the css files
        Create app.html with template

        ```
            <!DOCTYPE html>
            <html {{ HTML_ATTRS }}>
            <head {{ HEAD_ATTRS }}>
                {{ HEAD }}
                <!-- Import Ionicon icons & Google Fonts our Bootstrap theme relies on -->
                <link href="https://cdn.jsdelivr.net/npm/ionicons@2.0.1/css/ionicons.min.css" rel="stylesheet" type="text/css">
                <link href="//fonts.googleapis.com/css?family=Titillium+Web:700|Source+Serif+Pro:400,700|Merriweather+Sans:400,700|Source+Sans+Pro:400,300,600,700,300italic,400italic,600italic,700italic" rel="stylesheet" type="text/css">
                <!-- Import the custom Bootstrap 4 theme from our hosted CDN -->
                <!-- <link rel="stylesheet" href="//demo.productionready.io/main.css"> -->
                <link rel="stylesheet" href="/index.css">
            </head>
            <body {{ BODY_ATTRS }}>
                {{ APP }}
            </body>
            </html>
        ```

#### 1.4 Create layout components

In order to place the global components like the top nav bar and the footer, we can put it into pages/layout/index.vue

as the layout component.

#### 1.5 Import the login page

    - 1. create file pages/login/index.vue
    - 2. copy the template
    - 3. Configure the router in nuxt.config.js 
    - 4. Set different status when login and register

**Question: what's the difference between computed and methods**

#### 1.6 Import the rest pages
    - 1. profile
    - 2. settings
    - 3. editor
    - 4. article

#### 1.7 Optimize top nav
    - 1. Route and ui sync, accurate match 
    - 2. 


#### 1.8 Create api module
    - 1. npm i axios


### 2. login/register page logics





### Deploy
   1. Create project zip file

    Files need to be included in a zip file
    - 1. .nuxt
    - 2. static
    - 3. nuxt.config.js
    - 4. package.json
    - 5. package-lock.json

   2. Connect to remote server  ssh ubuntu@42.192.138.208
   Remote Path:  /home/ubuntu/uploaded_files

   3. Use scp command to transfer files
   ```
   scp .\Real_Word_nuxtjs.zip ubuntu@42.192.138.208:/home/ubuntu/uploaded_files
   ``` 
   4. Unzip the file
    ```
    unzip Real_Word_nuxtjs.zip
    ```
   5. Install npm on remote server

   ```
   sudo apt install npm
   ```
   6. npm i , install node_modules on remote server
   7. Start the server, npm run start 


External IP: 42.192.138.208:3000



### Auto-Deploy with pm2
  - 1. use pm2   npm install pm2 -g
  - 2. pm2 start npm -- start

### Auto-Deploy with github actions(CI/CD)

  - 1. Generate tokens: https://github.com/settings/tokens (github -> profile -> developer settings -> Personal access tokens)
  - 2. Configure the token to the project Secrets
  - 3. Enter repo -> settings -> Secrets -> add secrets -> paste the token
