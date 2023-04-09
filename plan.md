
THE FLOW
--------

1. user pastes list of postcodes in textbox #1, one per line

2. user pastes csv of postcodes with names in textbox #2

3. hits submit, which then disables submit button, and triggers a JS function

4. the mapbox API is called (in a parallel i/o way?) to find co-ordinates of postcodes, and objects are built, one per location

- data structure of target destination:

  { postcode: "W1 1AZ",
    destination: true,
    name: "destination name",
    long: "0.00001",
    lat: "50.0001"
    }

- data structure of origins/destinations:

  [ object, object, object ]

5. iterate through each origin