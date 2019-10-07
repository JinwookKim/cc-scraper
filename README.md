# What is this?
This is an npm module where it scrapes popular credit card webpages and try my best to neatly put the useful information into a clean data structure for people to use in their projects. Hopefully, it'll be useful to build out fin-tech applications 🙏

The vision is to build this out in multiple languages (next is Python, thirdly will be Rust).
But, after I am done with this javascript package, I will try to migrate this over to an actual live, hosted API.

Please look through the issues and projects tabs for the future plans of `cc-scraper`.

# cc-scraper
The [cc-scraper](https://github.com/JinwookKim/cc-scraper) library is used as an npm module or [Node.js](https://nodejs.org/en/) module.

## installation
Using npm:
```javascript
npm i -s cc-scraper
```

In Node.js:
```javascript
// Load the cc-scraper library
const cards = require('cc-scraper');

// Get Chase's 5% Cash Back Calendar information
cards.getChaseCashBackCal((error, result) => {
    console.log('chase result = ', result);
});

// Get Discover's 5% Cash Back Calendar information
cards.getDiscoverCashBackCal((error, result) => {
    console.log('discover result = ', result);
});
```

Output (something similar to):
```javascript
chase_result = [ { quarterName: 'January - March',
                   quarter: 1,
                   categoryNames: [ 'gas stations', 'tolls', 'drugstores' ],
                   categories: [ [Object], [Object], [Object] ] },
                 { quarterName: 'April - June',
                   quarter: 2,
                   categoryNames: [ 'grocery stores', 'home improvement stores' ],
                   categories: [ [Object], [Object] ] },
                 { quarterName: 'July - September',
                   quarter: 3,
                   categoryNames: [ 'gas stations', 'select streaming services' ],
                   categories: [ [Object], [Object] ] },
                 { quarterName: 'October - December',
                   quarter: 4,
                   categoryNames: [ 'department stores', 'paypal', 'chase pay' ],
                   categories: [ [Object], [Object], [Object] ] } ]

discover_result = [ { quarter: 1,
                      category: 'Grocery Stores',
                      terms:
                       'blah blah terms...' },
                    { quarter: 2,
                      category: 'Gas Stations, Uber and Lyft',
                      terms:
                       'blah blah terms...' },
                    { quarter: 3,
                      category: 'Restaurants and PayPal',
                      terms:
                       'blah blah terms...' },
                    { quarter: 4,
                      category: 'Amazon.com, Target and Walmart.com',
                      terms:
                       'blah blah terms...' } ]

```
Quarter 1: January - March  
Quarter 2: April - June  
Quarter 3: July - September  
Quarter 4: October - December  

There will be occasions where some quarters are missing. For example, in the output above is missing `quarter 4`. That is because on their website calendar, they haven't finalized quarter 4 categories that will attribute to the 5% cash back (at the time of this writing). Therefore, my code will neglect that quarter.

See the [source code](https://github.com/JinwookKim/cc-scraper) for more details.
