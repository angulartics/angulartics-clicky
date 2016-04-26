## angulartics-clicky

Clicky plugin for [Angulartics](https://github.com/angulartics/angulartics).

*NOTE* You must have a premium Clicky account for this plugin to function.

## Install

First make sure you've read installation and setup instructions for [Angulartics](https://github.com/angulartics/angulartics#install).

Then you can install this package either with `npm` or with `bower`.

### npm

```shell
npm install angulartics-clicky
```

Then add `angulartics.clicky` as a dependency for your app:

```javascript
require('angulartics')

angular.module('myApp', [
  'angulartics',
  require('angulartics-clicky')
]);
```

> Please note that core Angulartics doesn't export the name yet, but it will once we move it into [the new organization](http://github.com/angulartics).

### bower

```shell
bower install angulartics-clicky
```

Add the `<script>` to your `index.html`:

```html
<script src="/bower_components/angulartics-clicky/dist/angulartics-clicky.min.js"></script>
```

Then add `angulartics.clicky` as a dependency for your app:

```javascript
angular.module('myApp', [
  'angulartics',
  'angulartics.clicky'
]);
```

## Changes in the Clicky snippet

Make the following modifications to your Clicky configuration object when using this module.

- `pageview_disable` stops pageviews from being tracked. Angulartics should do this automatically.
- `history_disable` stops tracking of the back/forward button. Angulartics should track movement through your application's routes.


```js
<script type="text/javascript">
  var clicky_custom = {
    pageview_disable : 1,
    history_disable : 1
  };
  var clicky_site_ids = clicky_site_ids || [];
  clicky_site_ids.push(100000000);
  (function () {
    var s = document.createElement('script');
    s.type = 'text/javascript';
    s.async = true;
    s.src = '//static.getclicky.com/js';
    ( document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0] ).appendChild(s);
  })();
</script>
```

## Documentation

Documentation is available on the [Angulartics site](http://angulartics.github.io/).

## Development

```shell
npm run build
```

## License

[MIT](LICENSE)

