# notification-widget

> Made with create-react-library

[![NPM](https://img.shields.io/npm/v/notification-widget.svg)](https://www.npmjs.com/package/notification-widget) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

## Install (if published)

```bash
npm install --save notification-widget
```
## To check in local system
```bash
npm install
cd example && npm install && npm start
```

## Usage

```jsx
import React, { Component } from 'react'

import NotificationWidget, { Effect } from 'notification-widget'
import 'notification-widget/dist/index.css'

class Example extends Component {
  render() {
    return <NotificationWidget 
          className={className}
          effect={Effect.ROTATE_X}
          data={[]}
          onItemClick={() => {}}
          onCheck={() => {}}
          checked={[]}
          onMarkRead={() => {}}
          onMarkUnRead={() => {}}
        >
          // container elem
        </NotificationWidget>
  }
}
```
## Props
```
NotificationWidget.propTypes = {
  containerStyle: PropTypes.object,
  count: PropTypes.number,
  style: PropTypes.object,
  className: PropTypes.string,
  effect: PropTypes.array,
  fps: PropTypes.number,
  frameLength: PropTypes.number,
  onItemClick: PropTypes.func,
  theme: PropTypes.object,
  onClickItem: PropTypes.func,
  renderItem: PropTypes.func,
  data: PropTypes.arrayOf(PropTypes.object),
  onCheck: PropTypes.func,
  checked: PropTypes.array,
  onMarkRead: PropTypes.func,
  onMarkUnRead: PropTypes.func
}
```
  * `count`: Badge count, if `count < 1`, badge will not shown.

  * `containerStyle`: custom style of container

  * `style`: custom style of badge

  * `className`: className of badge

  * `effect`: effect of notification.
    effect array should be `[string, string, object, object]`.

    `effect[0]` will be applied to `transform` on first frame.
    `effect[1]` will be applied to `transform` on `frameLength`.
    `effect[2]` will be applied as `style[key] = value` on first frame.
    `effect[3]` will be applied to `style[key] = value` on `frameLength`.

    Pre defined effect is available as
      * `Effect.ROTATE_X`
      * `Effect.ROTATE_Y`
      * `Effect.SCALE`

  * `frameLength`: Frame length for `effect[1]` and `effect[3]` (default 30.0, 60.0fps/30.0 = 0.5 second)
  * `onItemClick`: callback on popop item
  * `theme`: to pass theme
  * `renderItem`: customize render item
  * `data`: list of data to render in popup, in array [{id: <uniq identifier>, desc: <string>, read: <boolean>}]
  * `onCheck`: callback on click of checkbox
  * `checked`: take all checked items identifier in arrat i.e ['1', '2']
  * `onMarkRead`: callback on click of `read` botton
  * `onmarkUnRead`: callback on click of `unread` button

## License

MIT © [sukanta-m](https://github.com/sukanta-m)
