# Create Order
Backend
server.js
create order modal
get /api/orders
post /api/orders
delete /api/orders/:id
Frontend
create types
types.js
CLEAR_ORDER, CLEAR_CART, CREATE_ORDER
create actions
actions/orderActions.js
createOrder(order)
clearOrder()
create reducers
reducers/orderReducers.js
case CREATE_ORDER
case CLEAR_ORDER
Update Cart Component
components/Cart.js
connect order, createOrder, clearOrder
form onSubmit={this.createOrder}
createOrder() this.props.createOrder(order)
closeModal() this.props.clearOrder()
render()
const { cartItems, order } = this.props;
{order && (}
Manage Orders
Add new page
Install react-router-dom
App.js
Import BrowserRouter, Route, Link
render()
BrowserRouter
Route path="/admin" component={AdminScreen}
Route path="/" exact={true} component={HomeScreen}
HomeScreen.js
AdminScreen.js
components/Orders.js
render()
Orders
Backend
server.js
app.get("/api/orders")
app.delete("/api/orders/:id")
Frontend
types.js
FETCH_ORDERS
actions/orderActions.js
fetchOrders()
reducers/orderReducers.js
case FETCH_ORDERS {orders: action.payload}
components/Orders.js
connect orders, fetchOrders
componentDidMount() fetchOrders
render()
!orders
Loading...
table orders
index.css
style orders

# Deploy Website

# Create MongoDB Cloud Database
Login to https://www.mongodb.com/cloud
Add database user
Left sidebar> Select Security > Database Access
Select Add New User button
Enter user name and password and click Add User
Add IP whitelist
Left sidebar > Select Security > Network Access
Select Add IP Address
Enter 0.0.0.0/0 in Whitelist Entry and click Confirm
Get connection string
Left sidebar > Select Altas > Cluster
Click Connect
Click Connect to your application
Click Copy button


# Step 2: Deploy On Heroku
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