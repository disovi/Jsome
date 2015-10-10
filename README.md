Make your JSON objects look AWESOME !!
====================================

![Jsome](https://raw.githubusercontent.com/Javascipt/Jsome/master/logo.png)

This package allows you to give style to your JSON on your console!

##Installation :

```bash
$ npm install jsome
```

##How does it work ?

on your nodejs application, when you need to console.log a json object, all you need to do is to use the jsome function

```javascript
    var jsome = require('jsome');
    jsome([{"id":1,"email":"Khalid@Morocco.ma","active":true},{"id":2,"email":"Someone@somewhere.com","active":false},{"id":3,"email":"chinese@bamboo.tree","active":true}]);
```

Then your json object will be displayed on the console in a pretty format with Awsome colors !
Here is the result :

![jsome](https://raw.githubusercontent.com/Javascipt/Jsome/master/examples/example1.png)

You can add some points to show levels of elements... very helpful when you are dealing with complex json objects

```javascript
    jsome.level.show = true;
```

![jsome](https://raw.githubusercontent.com/Javascipt/Jsome/master/examples/example2.png)

The object `jsome.level` has as default value the following json :

```javascript
  jsome.level = {
      'show'    : false
    , 'char'    : '.'
    , 'color'   : 'red'
    , 'spaces'  : 2
  }
```

You can change the level char, its color ( [see colors package](http://npmjs.org/package/colors) ) and the number of spaces for each level.

You can configure the colors of the displayed json by changing the values of the `jsome.colors` object which has as default these values.

```javascript
  jsome.colors = {
      'num'   : 'cyan'
    , 'str'	: 'magenta'
    , 'bool'  : 'red'
    , 'undef' : 'grey'
    , 'null'  : 'grey'
    , 'attr'  : 'green'
    , 'quot'  : 'yellow'
    , 'punc'  : 'yellow'
    , 'brack' : 'yellow'
  }
```

When you have a json as a string, instead of passing by JSON.parse function, you can just call the parse function of jsome

```javascript
  jsome(JSON.parse('[1,2,3]'));
```

becomes:

```javascript
  jsome.parse('[1,2,3]');
```

If you need to disable the colors:

```javascript
  jsome.params.colored = false;
```

When you have a very long json to display, don't make your code blocking... you can enable the asynchronous mode.

```javascript
jsome.global.async = true;

jsome(longJson, function () {
    /* Your code here */
});
```

The default value of `params` is:

```javascript
  jsome.params = {
      'colored' : true
    , 'async'   : false
  }
```

