### Places APP. 🧑‍💻

### Share your best places in one place.


![Places App](https://user-images.githubusercontent.com/74671966/204864826-904b6790-1cb8-45b6-8511-e59392068cc3.png)


![Places App](https://user-images.githubusercontent.com/74671966/204864893-87d4bbf1-3d60-40a8-b300-e32d982cbc9a.png)

![Screenshot 2022-11-30 at 19 34 32](https://user-images.githubusercontent.com/74671966/204868586-43d909ff-356c-4f40-b6e0-e4efd231939f.png)

...

### Link -> https://guedjcode-places-app.herokuapp.com/

### MERN APP => MongoDB, Express, React, NodeJS.

### App Functions:

\* Create a user => Name , Email , Password, Avatar.

\* Add a Place => Title, Description, Address, Image.

\* Edit Place => Title & Description.

\* Delete Place.

\* View on Google map the location via Google API.


# Quick Start 🚀

### Add a default.json file in config folder with the following

```json
{
  "mongoURI": "<your_mongoDB_Atlas_uri_with_credentials>",
  "jwtSecret": "secret",
  "Google_API":"YourGoolgeApiKey"
}
```

### Install server dependencies

```bash
npm install
```

### Install client dependencies

```bash
cd client
npm install
```

### Run both Express & React from root

```bash
npm run dev
```

### Build for production

```bash
cd client
npm run build
```

### Test production before deploy

After running a build in the client 👆, cd into the root of the project.  
And run...

Linux/Unix

```bash
NODE_ENV=production node server.js
```

Windows Cmd Prompt or Powershell

```bash
$env:NODE_ENV="production"
node server.js
```

Check in browser on [http://localhost:4000/](http://localhost:4000/)

### Deploy to Heroku

If you followed the sensible advice above and included `config/default.json` and `config/production.json` in your .gitignore file, then pushing to Heroku will omit your config files from the push.  
However, Heroku needs these files for a successful build.  
So how to get them to Heroku without commiting them to GitHub?

What I suggest you do is create a local only branch, lets call it _production_.

```bash
git checkout -b production
```

We can use this branch to deploy from, with our config files.

Add the config file...

```bash
git add -f config/production.json
```

This will track the file in git on this branch only. **DON'T PUSH THE PRODUCTION BRANCH TO GITHUB**

Commit...

```bash
git commit -m 'ready to deploy'
```

Create your Heroku project

```bash
heroku create
```

And push the local production branch to the remote heroku main branch.

```bash
git push heroku production:main
```

Now Heroku will have the config it needs to build the project.

> **Don't forget to make sure your production database is not whitelisted in MongoDB Atlas, otherwise the database connection will fail and your app will crash.**

After deployment you can delete the production branch if you like.

```bash
git checkout main
git branch -D production
```

Or you can leave it to merge and push updates from another branch.  
Make any changes you need on your main branch and merge those into your production branch.

```bash
git checkout production
git merge main
```

Once merged you can push to heroku as above and your site will rebuild and be updated.

Enjoy.
