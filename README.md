![logo](logo.png)

# ADVPL - a language grammar for [highlight.js](https://highlightjs.org/)

ADVPL is the programming language developed by TOTVS, which runs mainly on the ERP TOTVS Protheus.

## Usage

Simply include the Highlight.js library in your webpage or Node app, then load this module.

### Static website or simple usage

Simply load the module after loading Highlight.js. You'll use the minified version found in the `dist` directory. This module is just a CDN build of the language, so it will register itself as the Javascript is loaded.

```html
<script type="text/javascript" src="/path/to/highlight.min.js"></script>
<script type="text/javascript" charset="UTF-8"
  src="/path/to/highlightjs-advpl/dist/advpl.min.js"></script>
<script type="text/javascript">
  hljs.highlightAll();
</script>
```

### Using directly from the UNPKG CDN

```html
<script type="text/javascript"
  src="https://unpkg.com/highlightjs-advpl/dist/advpl.min.js"></script>
```

- More info: <https://unpkg.com>

### With Node or another build system

If you're using Node / Webpack / Rollup / Browserify, etc, simply require the language module, then register it with Highlight.js.

```javascript
var hljs = require('highlightjs');
var hljsadvpl = require('highlightjs-advpl');

hljs.registerLanguage("advpl", hljsadvpl);
hljs.highlightAll();
```

### React

You need to import both Highlight.js and third-party language like advpl:

```js
import React, {Component} from 'react'
import 'highlight.js/scss/darcula.scss' # your favourite theme
import advpl from './advpl'
import hljs from 'highlight.js'
hljs.registerLanguage('advpl', advpl);

class Highlighter extends Component
{
  constructor(props)
  {
    super(props);
    hljs.highlightAll();
  }

  render()
  {
    let {children} = this.props;
    return
    {
      <pre ref={(node) => this.node = node}>
        <code className="advpl">
          {children}
        </code>
      </pre>
    }
  }
}

export default Highlighter;
```

## License

Highlight.js is released under the CC0 1.0 License. See [LICENSE][1] file
for details.

### Author

Matheus Nogueira <matheus.nogueira@totvs.com.br>

### Maintainer

Matheus Nogueira <matheus.nogueira@totvs.com.br>

## Links

- The official site for the Highlight.js library is <https://highlightjs.org/>.
- The Highlight.js GitHub project: <https://github.com/highlightjs/highlight.js>
- Learn more about ADVPL: <https://www.totvs.com/blog/developers/advpl/>

[1]: https://github.com/matheusnogueira/highlightjs-advpl/blob/main/LICENSE
