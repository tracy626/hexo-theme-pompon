**add `tag.register('bilibili', require('./bilibili'));` in `\node_modules\hexo\lib\plugins\tag\index.js`**

Also, need to add `bilibili.js` in `\node_modules\hexo\lib\plugins\tag`

```bash
'use strict';

/**
* BILIBILI tag
*
* Syntax:
*   {% bilibili av_id %}
*/

function bilibiliTag(args, content) {
  var id = args[0];

  return '<div class="video-container"><iframe src="https://static.hdslb.com/miniloader.swf?aid=' + id + '" allowfullscreen="true"></iframe></div>';
}

module.exports = bilibiliTag;
```
