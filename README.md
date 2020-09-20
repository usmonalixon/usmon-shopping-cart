Create git repository in amazona folder using git init
Create Heroku Account at heroku.com
Heroku
Create Heroku account on heroku.com
Install Heroku cli https://devcenter.heroku.com/articles/heroku-cli
Open Terminal
heroku login
heroku apps:create react-shopping-cart-best
Edit package.json
"engines": { "node": "12.4.0", "npm": "6.9.0"}
Create Procfile
web: node server.js
Set MongoDB connection string in Heroku
Open Heroku apps https://dashboard.heroku.com/apps/
Select your apps, open Setting Tab and click Reveal Config Vars
Add key MONGODB_URL
Enter copied connection string from the previous step
Update database name and username and password
Add key NODE_MODULES_CACHE and value false
app.use("/", express.static(__dirname + "/build"));
app.get("/", (req, res) => res.sendFile(__dirname + "/build/index.html"));
git add . && git commit -m "publish"
git push heroku