```bash
<embed width="750" height="624" pluginspage="http://www.adobe.com/shockwave/download/download.cgi?P1_Prod_Version=ShockwaveFlash" src="http://share.acg.tv/flash.swf?aid=xxxxx&amp;page=1" type="application/x-shockwave-flash" quality="high" wmode="transparent" menu="false" allowfullscreen="true" flashvars="autostart=false">
```

To change the `id=xxxxx`.
`xxxxx` should be av number of the video in bilibili.com

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

  return '<div class="video-container"><embed width="750" height="624" pluginspage="http://www.adobe.com/shockwave/download/download.cgi?P1_Prod_Version=ShockwaveFlash" src="http://share.acg.tv/flash.swf?aid=' + id + '&amp;page=1" type="application/x-shockwave-flash" quality="high" wmode="transparent" menu="false" allowfullscreen="true" flashvars="autostart=false">';
}

module.exports = bilibiliTag;
```