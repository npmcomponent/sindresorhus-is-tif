*This repository is a mirror of the [component](http://component.io) module [sindresorhus/is-tif](http://github.com/sindresorhus/is-tif). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/sindresorhus-is-tif`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# is-tif [![Build Status](https://travis-ci.org/sindresorhus/is-tif.svg?branch=master)](https://travis-ci.org/sindresorhus/is-tif)

> Check if a Buffer/Uint8Array is a [TIFF](http://en.wikipedia.org/wiki/Tagged_Image_File_Format) image

Used by [image-type](https://github.com/sindresorhus/image-type).


## Install

```sh
$ npm install --save is-tif
```

```sh
$ bower install --save is-tif
```

```sh
$ component install sindresorhus/is-tif
```


## Usage

##### Node.js

```js
var readChunk = require('read-chunk'); // npm install read-chunk
var isTif = require('is-tif');
var buffer = readChunk('unicorn.tif', 0, 4);

isTif(buffer);
//=> true
```

##### Browser

```js
var xhr = new XMLHttpRequest();
xhr.open('GET', 'unicorn.tif');
xhr.responseType = 'arraybuffer';

xhr.onload = function () {
	isTif(new Uint8Array(this.response));
	//=> true
};

xhr.send();
```


## API

### isTif(buffer)

Accepts a Buffer (Node.js) or Uint8Array.

It only needs the first 4 bytes.


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
