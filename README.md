# RestaurantAPI

**I. HIGH-LEVEL OVERVIEW - ENGINEERING CHOICES**

**FLASK**

Selected this framework based on its wide use and popularity among the Python Dev community. It guarantees easier, scalable, efficient and maintainable web applications by providing reusable code or extensions for common operations.. 

**DB MODEL**

**Restaurant** table with the following attributes:


    restaurant_id = db.Column(db.Integer, primary_key=**True**)
    restaurant_name = db.Column(db.String(200), index=**True**, unique=**True**)
    website = db.Column(db.String(300), unique=**True**)
    address = db.Column(db.String(200))
    phone = db.Column(db.Integer, unique=**True**)
    creation_date = db.Column(db.DateTime, default=datetime.utcnow)
    expiration_date = db.Column(db.DateTime)
    opening_time = db.Column(db.Integer)
    closing_time = db.Column(db.Integer)
    is_open = db.Column(db.String, default=**'Closed'**)

**API ENDPOINTS**


    GET
    /api/restaurants/{restaurant_name}

    POST
    /api/restaurants

**HTPPie** 

Tool for testing the API

**II. EXECUTION INSTRUCTIONS**

Use HTTPie to run the following GET and POST commands to test the application:


    http GET http://localhost:5000/api/restaurants/'ChowNow Sushi’

    http GET http://localhost:5000/api/restaurants/'ChowNow Burgers’

    http POST http://localhost:5000/api/restaurants restaurant_name=Treehouse website=treehouse.com address=Carmel phone=831.123.4444 opening_time=10 closing_time=22

**III. NEXT STEPS (TODOs)**

    1. Organize the application structure better in Flask
    2. Normalize the DB, expand the Restaurant table and add other relevant attributes. create additional tables such as an Address table
    3. Add unit tests
    4. Allow lookup of more than 1 restaurant or all restaurants
    5. Add Put and Delete Endpoints
    6. Update the logic for setting the “is_open” attribute by using the user timezone, and restaurant location/address to validate if the restaurant is open or closed

**IV. NOTE**

This is the first project where I used Flask, SQLLite and for a Python REST API. 
