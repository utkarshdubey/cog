# Cog 📐
Cog is an open-source library which acts like a templating engine for easy DOM insertion. It requires some native libraries such as `filesystem` to work properly. Cog can be used in code which works in isolated environment like **Chrome Extensions**, pure javascript dependent code system, etc.

## Installation
You can install **Cog** with including the minified/non-minified version of the compiled file which is available in the `dist` folder.
You can also install it by using `yarn` or `npm` by doing:
``yarn add cog`` or ``npm install cog``. You can also directly use the files or through [Unpkg](https://unpkg.com).

## Documentation
Cog is easy to initialize in your project with only two lines to include.
```js
const cog = require('cog');
cog.init();
```
If you work in an isolated environment where the files are stored locally, you can require them with a relative path like this.
```js
const cog = require('../dist/cog.min.js');
cog.init();
```
### Inserting html content inside the DOM
Inserting `HTML` content has been painful because either you are going the native way where its damn complex to write minimal code, or you are stuck with libraries which have other useless stuff and increases your file size. Cog makes it easy by allowing to implement `HTML` directly into the DOM. You have to first create a `views` folder inside your project root or if you want to override the default folder you can do it like this:-
```js
...
cog.init();
cog.setDefaultFolder('/path/to/folder')
...
```
After initializing the folder, you can now use the HTML to insert into the DOM.
To access the HTML from the files, you can do it by:-
```js
cog.fetchHTML('file.html', {
	data:[
	{
		"key": 1,
		"name": "John Doe",
	},
	{
		"key": 2,
		"name": "Jane Doe"
	},
	{
		"key": 3,
		"name": "George Doe"
	}
]
});
```
In the html you can easily use the JS variables inside the HTML file using this template literal:
```html
...
<some-element>
<p>{{cog.data.YOUR_VARIABLE_NAME}}
</some-element>
...
```
Cog uses default rendering for faster render time and inserts the variables after the element is inserted into the DOM.

You can also insert the custom CSS files using  cog by initializing a css file through the following code:-
```js
cog.addCSS('/path/to/css/file');
```

## Contributing
If you plan to contribute on this project or improve the existing features, we are pleased to have you on board. You can do so by adding your name to the CONTRIBUTING.md file and making a pull request. Thanks for reading this documentation.

## License
Copyright 2019 Shimasu

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE. 