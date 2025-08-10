The program - CREATE A BETTER CLASS - modifies the GEO POINT (refers to [MlengelaPD6](https://github.com/CIS1250Python/MlengelaPD6.git)) so that it has a default constructor and some properties. 
1. In the GeoPoint Class, I make the following changes (Note: variables, parameters, and method names may be different):
      * Add a constructor _init_(self, lat=0, lon=0, description ='TBD') that will initialize the class variables self.lat, self.lon, and the self.description.
        Notice that the constructor will also default lat and lon to zero and description to 'TBD' if they are not provided.
      * Change the SetPoint method so that instead of individual coordinates SetPoint(_self_, lat, lon) it takes a single sequence/tuple/list.SetPoint(self,point)
                 *self.lat=point[0]
                 *self.lon=point[1]
      * Add a property: point=property(GeoPoint, SetPoint). Make sure GetPoint and SetPoint are the names used for the get and set methods.
      * Add another property: description=property(GetDescription, SetDescription). Make sure GetDescription and SetDescription are the names used for the get and set methods.
      * Change the distance method so that it takes a GeoPoint instead of coordinates: calcDistance(self, point) instead of Distance(self, lat, lon)
                 * lat1=math.radians(self.lat)
                 * lon1=math.radians(self.lon)
                 * lat2=math.radians(point.lat)
                 * lon2=math.radians(point.lon)
2. In the main part of the program, there are the following:
      * Include the class
      * Instantiate two points
      * Instead of using SetPoint and SetDescription methods to set each of the points' locations and descriptions, there are the following:
               i.	Ask the user for their location: latitude, longitude, and description of location.
              ii.	Create a third point to represent the user’s location. You can use either the constructor or the properties. With a constructor, it will look something like the following:
                  pointUser = GeoPoint(lat,lon, 'User Location')
             iii.	Use point1 and point2’s Distance method to find the distance from each point to the user’s location. Notice we are passing in the user's point rather than the separate coordinates:
                         distanceToOne = point1.calcDistance(pointUser)
                         distanceToTwo = point2.calcDistance(pointUser)
             iv.	Tell the user which point they are closest to in this format:
        
        You are closest to <description>, which is located at <point’s x, y, z coordinates>
        
        v.	Ask “Do another (y/n)?” and loop if they respond with ‘y’.
 
