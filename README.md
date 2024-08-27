# chichi-pui_Imagus
Imagus Sieve for chichi-pui.com

This is a sieve definition to enable Imagus on chichi-pui, a post and generation site dedicated to AI images.  
[Imagus](https://www.reddit.com/r/Imagus) is a browser extension that enlarge thumbnails, and show images/videos from links with a mouse hover.  

![ss_2024-08-27](https://github.com/user-attachments/assets/7d268f09-1393-44ea-a9ba-d7348792e9b2)

Show in text below.

* link
```
^(chichi-pui\.com/posts/.+/)
```

* res
```
:
var re = /^(.+)\?.+/;
var ret=[],x=(new window.DOMParser()).parseFromString($._,'text/html').querySelectorAll('a.js-main-image-link');
for(var i=0,l=x.length;i<l;i+=1)
  ret.push([x[i].href.replace(re, "$1")]);
return ret
```

* img
```
^(chichi-pui\.imgix\.net/uploads/post_images/.+)\?.+
```

* to
```
$1
```
In the future, if the site's coding changes, we may need to modify the 'a.js-main-image-link' part.
