# converter [![NPM version](https://badge.fury.io/js/converter.png)](http://badge.fury.io/js/converter)  [![Build Status](https://github.com/assemble/converter.png)](https://github.com/assemble/converter)

> Convert between XML, JSON and YAML, from one format to another.

## Getting Started
To install the module, run the following in the command line:

```bash
npm i converter --save
```

Use within your application with the following line of JavaScript:

```js
var converter = require('converter');
```

Calling `var convert = converter(options);` gives you a `transform` stream that will take in data and convert it based on the options passed in.

```js

var fs = require('fs');
var converter = require('converter');

// get a file stream reader pointing to the csv file to convert
var reader = fs.createReadStream('path/to/csv/file.csv');

// get a file stream writer pointing to the json file to write to
var writer = fs.createWriteStream('path/to/output/json/file.json');

// setup the options for the data converter
var options = {
	from: 'csv',
	to: 'json'
};

// get a data converter stream using the given options
var convert = converter(options);

// pipe everything to do the conversion
reader.pipe(convert).pipe(writer);

```


## Contributing
Find a bug? Have a feature request? Please [create an Issue](https://github.com/assemble/converter/issues).

In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [grunt][], and build the documentation with [grunt-readme](https://github.com/assemble/grunt-readme).

Pull requests are also encouraged, and if you find this project useful please consider "starring" it to show your support! Thanks!


## Author

**Jon Schlinkert**

+ [github/jonschlinkert](https://github.com/jonschlinkert)
+ [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

**Brian Woodward**

+ [github/doowb](https://github.com/doowb)
+ [twitter/doowb](http://twitter.com/jonschlinkert)


## Related
+ [helpers](https://github.com/helpers): some great handlebars helpers that we decided not to include in the [handlebars-helpers](https://github.com/assemble/handlebars-helpers) project, most likely because the code footprint was too big or the helper wasn't generic enough.


## License
Copyright (c) 2014 Brian Woodward, contributors.
Released under the  license

***

_This file was generated by [grunt-readme](https://github.com/assemble/grunt-readme) on Monday, January 13, 2014._

[grunt]: http://gruntjs.com/
[Getting Started]: https://github.com/gruntjs/grunt/blob/devel/docs/getting_started.md
[package.json]: https://npmjs.org/doc/json.html
