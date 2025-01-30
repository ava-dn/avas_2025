Sprint 5 Blog

My group's program has a quiz the user can take that matches them to a national park 

and is personal to the user. The user can then go and find more information 

about their national park. By answering a series of questions, users 

are taken on a journey that helps them identify which park aligns with 

their tastes, adventure level, and outdoor preferences. The quiz takes into

account factors like preferred activities (e.g., hiking, wildlife watching, 

or scenic drives), & weather preferences.and terrain. The user can also review 

the national park as well as give it a star rating. The user can also use the 

interactive Google Maps api system on each page.



My purpose in Sprint 5 has been designing and developing all 4 of the national park pages, 

integrating both interactive elements and visual enhancements to create an engaging user 

experience. These pages serve as a comprehensive resource, offering an array of features 

that bring the beauty and information of these parks to life. I also integrated a google 

maps API system on each individual page that allows the user to pin points, that fetches 

lat/lg points, and the user can delete pin as well.

**AP REQUIREMENTS**
In your program, you must include student-developed program code that
contains the following:
Instructions for input from one of the following:
- the user (including user actions that trigger events)
- a device
- an online data stream
- a file









1. Formatting Response Data (JSON) into the DOM
When the API sends location data as JSON (like id, lat, lng, and timestamp), the frontend uses JavaScript (e.g., with fetch or Axios) to get this data. It then uses the DOM methods like innerHTML or createElement to display the data on the webpage. This ensures that the user sees the most recent location data from the backend.

GET REQUEST
def get(self):
    locations = Location.query.all()
    if not locations:
        return {'message': 'No locations found'}, 404
    return jsonify([location.read() for location in locations]), 20

2. Queries from Database (Python List of Rows)
Using SQLAlchemy, a Python library, database queries retrieve a list of rows from the locations table. For example, calling Location.query.all() fetches all location records and returns them as Python objects, which are easily processed and converted to dictionaries for JSON output.

locations = Location.query.all()

The Location.query.all() method returns a Python list of Location objects, where each object represents a row in the locations table.


3. Methods in "Class" to Work with Columns (CRUD)
The Location class has methods for CRUD operations. create() saves new records, read() converts the object into a dictionary for JSON, update() modifies existing records, and delete() removes records from the database. These methods simplify working with the database.

CRUD: 
def create(self):
        db.session.add(self)
        db.session.commit()

    def read(self):
        return {
            "id": self.id,
            "name": self._name,
            "channel_id": self._channel_id,
            "attributes": self._attributes,
            "lat": self.lat,
            "lng": self.lng,
            "timestamp": self.timestamp.isoformat(),
        }

    def update(self, inputs):
        if 'name' in inputs:
            self._name = inputs['name']
        if 'channel_id' in inputs:
            self._channel_id = inputs['channel_id']
        if 'attributes' in inputs:
            self._attributes = inputs['attributes']
        if 'lat' in inputs:
            self.lat = inputs['lat']
        if 'lng' in inputs:
            self.lng = inputs['lng']

        db.session.commit()

    def delete(self):
        db.session.delete(self)
        db.session.commit()

4. Algorithmic Code Request (Request Handling)
The backend handles requests using methods like post() and get(). For instance, post() creates a new location, and get() retrieves all locations. These methods check for missing or incorrect data and return responses accordingly.

def post(self):
    data = request.get_json()

    if not data or 'lat' not in data or 'lng' not in data or 'user_id' not in data:
        return {'message': 'Missing required fields (lat, lng, user_id)'}, 400

    # Create a new location
    location = Location(lat=data['lat'], lng=data['lng'], user_id=data['user_id'])
    location.create()

    return jsonify(location.read()), 201

This method handles the POST request to create a new location, validating the data and sending back a response.

5. API Class for Get, Post, Put, and Delete Methods
The LocationAPI class handles HTTP methods using Flask-RESTful. It defines routes and links them to actions like creating a new location (POST), getting locations (GET), updating locations (PUT), and deleting a location (DELETE). These routes are set up in the api.add_resource() method.

class LocationAPI:
    class _CRUD(Resource):
        @token_required
        def post(self):
            # Handle location creation
            ...
        
        @token_required
        def get(self):
            # Handle fetching locations
            ...
        
        @token_required
        def delete(self):
            # Handle deleting a location
            ...
    
    api.add_resource(_CRUD, '/locations')

This LocationAPI class uses Flask-RESTful to define routes and methods for handling the full range of HTTP operations (GET, POST, DELETE).

6. Method with Sequencing, Selection, and Iteration
The get() method retrieves all locations with Location.query.all(), iterates over them, and serializes each location using the read() method. It handles whether any locations are found, returning a JSON response accordingly.

def get(self):
    locations = Location.query.all()
    if not locations:
        return {'message': 'No locations found'}, 404

    return jsonify([location.read() for location in locations]), 200

This method performs sequencing (iterating over each Location object), selection (checking if any locations exist), and iteration (looping through the list of locations to generate the JSON response).


7. Parameters (Body of Request) and Return Type (jsonify)
The post() method expects a JSON body with lat, lng, and user_id. It returns a JSON response using jsonify() to send back the created location or an error message if data is missing or invalid.

def post(self):
    data = request.get_json()
    if not data or 'lat' not in data or 'lng' not in data or 'user_id' not in data:
        return {'message': 'Missing required fields'}, 400

    # Create location
    location = Location(lat=data['lat'], lng=data['lng'], user_id=data['user_id'])
    location.create()

    return jsonify(location.read()), 201 

    The POST method accepts parameters in the request body (lat, lng, and user_id) and returns a JSON response with the newly created location.


8. Call to Algorithm Request (Request Definition)
To create a new location, the frontend sends a POST request with data like lat, lng, and user_id. The request is sent via fetch() or Axios, triggering the backend to store the new location in the database.

fetch('/api/location', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer token'
  },
  body: JSON.stringify({ lat: 40.7128, lng: -74.0060, user_id: 1 })
})
  .then(response => response.json())
  .then(data => console.log(data));

This example shows how to make a POST request from the frontend to the backend API to create a new location.

9. Return/Response from Method and Data Handling
The backend returns a response in JSON format. If the request is successful, it sends the new location data. If there’s an error (e.g., missing fields), it sends an error message. The frontend handles this response, updating the DOM accordingly.

return jsonify(location.read()), 201

The backend returns the newly created location as JSON. In case of an error, the response will include an error message and status code (400 or 404).


10. Changing Data or Method Triggers Different Responses
Changing the data or method in the request can trigger different responses. For example, if required data is missing in a POST request, the backend will return an error (400 Bad Request). If the request is successful, the response will indicate success (201 Created). Different HTTP status codes are used to handle errors or successful actions.

if not data or 'lat' not in data or 'lng' not in data or 'user_id' not in data:
    return {'message': 'Missing required fields'}, 400

If the data sent in the request is incomplete or invalid, the backend responds with a 400 error.
