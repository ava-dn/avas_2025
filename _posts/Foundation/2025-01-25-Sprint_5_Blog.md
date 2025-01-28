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