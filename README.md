

Learnt alot about the quirks of Javascript's asynchronous execution as
a result of the API calls involved in this project.

Async functions always return a promise, and it is hard to unpack a
promise once returned to a synchronous function. I figured out a
workaround to get back to synchronous execution
by using something along the lines of:

    const final_result = [];

    main() {

        Promise.all([ promise_a, promise_b ]).then(
	    (result) => main_part_two(result)
	);

    }

    main_part_two(result) {

        final_result = result;

    }

This may be incorrect usage, but my use of async is heavily influenced
by experiences with Python3, which feels more under control.

However, I can vaguely imagine how if you programmed in a more
functional-programming way, there would be less need to claw back to
synchronous execution in the same way. But despite reading Douglaw
Crockford's book, an avid proponent of functional programming, it is
not so clear to me yet how to do that with Javascript.

Admittedly, all tests were done by eye, following the console, as
after reading through Douglas Crockford's book, then reading through
the Vue.js documentation, then beginning with experimenting, there
wasn't alot of time left to read over how the 'Jest' testing library
works, to write unit tests. I also have not figured out how to split
Javascript functions across files and still have them compatible with
Vue.

The rough estimate of converting the co-ordinate based distance to the
kilometer distances is based on the following fact:

London -> Edinburgh is 534 km
The co-ordinate distance is 5.4

So multiply co-ordinate distance by 99 and round to nearest integer.

Regarding data structures, all the functions revolve around gradually
building up the below array of objects. There is a little data
duplication, but inevitably destination info has to be stored amongst
origin info, so it was just simpler to store all of it.

[
  {
    "postcode": "SW1A 0AA",
    "long": -0.124663,
    "lat": 51.49984,
    "dests": [
      {
        "postcode": "N1C 4BA",
        "name": " Kings Cross St. Pancras",
        "long": -0.128253,
        "lat": 51.538098,
        "distance": 0.038426067506315616
      },
      {
        "postcode": "EH1 1BB",
        "name": " Edinburgh Waverley",
        "long": -3.188448,
        "lat": 55.952347,
        "distance": 5.4047753987815295
      }
    ]
  },
  {
    "postcode": "WC2A 2LL",
    "long": -0.113546,
    "lat": 51.513645,
    "dests": [
      {
        "postcode": "N1C 4BA",
        "name": " Kings Cross St. Pancras",
        "long": -0.128253,
        "lat": 51.538098,
        "distance": 0.02853497955142175
      },
      {
        "postcode": "EH1 1BB",
        "name": " Edinburgh Waverley",
        "long": -3.188448,
        "lat": 55.952347,
        "distance": 5.399731266869496
      }
    ]
  },
  {
    "postcode": "EC4M 8AD",
    "long": -0.099166,
    "lat": 51.51425,
    "dests": [
      {
        "postcode": "N1C 4BA",
        "name": " Kings Cross St. Pancras",
        "long": -0.128253,
        "lat": 51.538098,
        "distance": 0.03761357033040132
      },
      {
        "postcode": "EH1 1BB",
        "name": " Edinburgh Waverley",
        "long": -3.188448,
        "lat": 55.952347,
        "distance": 5.407436384917816
      }
    ]
  }
]

