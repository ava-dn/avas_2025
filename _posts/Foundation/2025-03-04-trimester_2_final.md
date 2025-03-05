# **Tri 2 Final 🎉**


5 things I did 



#1 I worked on a lot of the frontend for the various national park pages: the image scrollers,

 hiking trails, wildlife and styling


#2 I completed various blogs on the college board main ideas to put in my personal so I can 

look back on them in the future 


#3 I created a Google Maps API system for each national park using google cloud developer


#4 I completed a large part of our group’s major deployment blog that is on our site in the 

about section 


#5 I completed an at home night at the museum reviewing 5 different people (my group got 

feedback from about 20 people) and was an active contributor in the planning process of the project 

—----------------------

MY CODE: 

<img src="{{site.baseurl}}/images/pppp.png" alt="beginning of code">



explanation of api code:


lines 1-8 blueprint

---------------

lines 8-14  Defines a Flask Blueprint for the location API with a base URL , 

An instance of Api attached to the location_api Blueprint.


--------------


<img src="{{site.baseurl}}/images/mm.png" alt="end of code">


POST Request: The user sends their location (latitude and longitude) to 

store or update it.

Post REQUEST

@token_required()
def post(self):

-------------

Get request

@token_required()
def get(self):

----------------------

The @token_required decorator ensures authentication.

Retrieves the user's location from the database using Location.query.

filter_by(user_id=current_user.id).first().

If no location is found, a 404 error is returned.

If the location is found, it returns the location data.


------------------

_ALL_LOCATIONS Resource


This endpoint is for admin users to access all stored locations.

class _ALL_LOCATIONS(Resource):
    def get(self):

It retrieves all location entries from the database using Location.query.all

().

Returns a list of all locations as JSON.


-----------------


Mapping API Resources

api.add_resource(LocationAPI._CRUD, '/location')

api.add_resource(LocationAPI._ALL_LOCATIONS, '/locations')

Maps the endpoints to the corresponding resources.

/api/location is mapped to the LocationAPI._CRUD resource for handling 

individual user locations.

/api/locations is mapped to the LocationAPI._ALL_LOCATIONS resource for 

accessing all stored locations.


---------------------



<img src="{{site.baseurl}}/images/Screenshot 2025-03-05 094701.png" alt="working in postman">






------------------------

**CPT REQUIREMENTS:**


self.location_history.append({"user_id": user_id, "location": location, "review": review})


Explanation: This code adds a user's location and associated review to the location_history list,

helping track the user's pinned locations and reviews over time.

Student-Developed Procedure
 
def save_location(self, user_id, latitude, longitude, review):

Explanation: This function allows users to save a specific location (latitude and longitude) 

along with their review. It stores this information in the system, enabling users to return to 

the same spot later.



Algorithm (Sequencing, Selection, Iteration)


Code Snippet


try:
    location_data = request.get_json()
    
    if not location_data or 'latitude' not in location_data or 'longitude' not in
    
     location_data:
        return jsonify({"error": "Latitude and Longitude are required"}), 400



Explanation: This is an example of selection in the code. It checks if the necessary

 data (latitude and longitude) is provided in the request. If not, an error message is returned.


Procedure Call


location_response = self.save_location(user_id, latitude, longitude, review)

Explanation: This calls the save_location() method to store the user’s location and review based on the 

data received. It saves the data to the database and returns a response indicating the success or 

failure of the operation.



Output Statement

return jsonify({"message": "Location saved successfully", "location": location_response})


Explanation: This sends a confirmation message back to the user, including the saved location data, 

in JSON format. It lets the user know their location and review have been successfully saved.






**FRQ PRACTICE:**


BLOG WRITE UP:  the Google Maps API I created allows users to interact 

with a map. When a user clicks on a specific point on the map, the 

latitude and longitude points of that specific spot are captured.

 These coordinates are then stored in a database, allowing the user
 
  to save the location and stay there after reloading the page. 
  
  This functionality enhances the user experience by providing 
  
  an interactive interface for location-based data collection.




MC



<img src="{{site.baseurl}}/images/Screenshot 2025-03-05 095458.png" alt="working in postman">








<img src="{{site.baseurl}}/images/Screenshot 2025-03-05 095321.png" alt="working in postman">



Personal Night at the Museum Feedback:


#1 Talya - 


Post and review system seem a little redundant as they both have a very similar functionality. 

Loves the different images of each park, says they contribute to the page a lot and

adds life to the project



#2 My dad - 


He loves camping so he especially enjoyed the camping post feauture where you pick the

biome of your park and write about yor experience ther so others can see it.

Thought the page was a little confusing to navigate



#3 My brother

Enojoyed the google maps api and the star system, made it seem really 

professional as that is a common feature on professional websites


#4 My sister 

Loved the designing of the page 



#5 Sharon -

Enjoyed the quiz and thought it was very accurate and a very interactive user experience

(tried it out herself)


The gemini did not work as expected when we tried it 



COMP SCI FINAL →


Talk with sharon 


Im considering comp sci A, computer science A is more of a classwide project 

learning more about communication and 

getting through small errors because lots of different people committing. 

More about organization and planning, java instead python


Sharon wants to take cognitive science, which uses computer science which is 

important in college and the future. I thought just a computer science major 

involves comp sci, didnt know it incorporates other majors




Self Grade: 0.925


Why:


➡️ Attendance: always one of the first ones here on time and prepared

➡️ Work Ethic: I always contributed during the live reviews and my work was 

always completed on time

➡️ Office hours: Came to CSP tutoring many times to get help 

➡️ Reaching Out: Met with sharon from Comp sci A, practiced live reviews 

compared projects, talked about how comp sci has helped her



A few key takeaways from this class



⭐ COMMUNICATION

⭐ SPEAKING

⭐ WORKING AS A GROUP

⭐ ACCOUNTABILITY