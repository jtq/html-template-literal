# Usage

## Use predefined HTML tags

### Simple

```
import { span } from 'html-template-literal';

span`Content`
```
Results in:
```
<span>Content</span>
```

### With attributes

```
import { span } from 'html-template-literal';

span({class:'note'})`Content`
```
Results in:
```
<span class="note">Content</span>
```

### Nested

```
import { div, span } from 'html-template-literal';

div({class:'header', style:'color:grey'})`
  Outer div
  ${span({title:'Title'})`
    Inner span
  `}
  Outer div again
`
```
Results in:
```
<div class="header" style="color:grey">
  Outer div
  <span title="Title">
    Inner span
  </span>
  Outer div again
</div>
```

## Define your own tags

### Simple tag

```
import { tag } from 'html-template-literal';

const simpleH1 = tag('h1');
simpleH1({title:'Tooltip'})`Heading text`
```
Results in:
```
<h1 title="Tooltip">Heading text</h1>
```

### Tag with predefined attributes

```
import { tag } from 'html-template-literal';

const h1WithTitle = tag('h1')({title:'Tooltip'});
h1WithTitle`Heading text`
```
Results in:
```
<h1 title="Tooltip">Heading text</h1>
```

## Define and use tags inline

```
import { tag } from 'html-template-literal';

tag('a')({href:'http://www.google.com'})`Anchor text`
```
Results in:
```
<a href="http://www.google.com">Anchor text</a>
```