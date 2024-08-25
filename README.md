# chichi-pui_Imagus
Imagus Sieve for chichi-pui.com

This is a sieve definition to enable Imagus on chichi-pui, a post and generation site dedicated to AI images.  
[Imagus](https://www.reddit.com/r/Imagus) is a browser extension that enlarge thumbnails, and show images/videos from links with a mouse hover.  

![ss_2024-08-25](https://github.com/user-attachments/assets/772aeb5d-ad8b-4fb0-a25a-f3d084507df8)
Show in text below.

* link
```
(/posts/.+/)
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

In the future, if the site's coding changes, we may need to modify the 'a.js-main-image-link' part.
