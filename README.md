### FileAPI
---
https://github.com/mailru/FileAPI

```js
var choose = document.getElementById('choose');
FileAPI.event.on(choose, 'change', function(evt){
  var files = FileAPI.getFiles(evt);
  FileAPI.filterFiles(files, function(file, info/**/){
    if( /^image/.test(file.type) ){
      return info.width >= 320 && info.height >= 240;
    }
    return false;
  }, function(files/**/, rejected/**/){
    if( files.length ){
      FileAPI.each(files, function(file){
        FileAPI.Image(file).preview(100).get(function(err, img){
          images.appendChild(img);
        });
      });
      FileAPI.upload({
        url: './ctrl.php',
        files: { images: files },
        progress: function(evt){ /**/ },
        complete: function(err, xhr){ /**/ }
      });
    }
  });
})

window.FileAPI = {
  debug: false
  , cors: false
  , media: false
  , staticPath: '/js/FileAPI/'
  , postNameConcat: function(name, idx){
    return name + (idx != null ? '[' + idx + ']' : '');
  }
};

window.FileAPI = { /**/ };
require(['FileAPI'], function (FileAPI){
});

var el = document.getElement('my-input');
FileAPI.event.on(el, 'change', function(evt/**/){
  var files = FileAPI.getFiles(el);
  var files = FileAPI.getFile(evt);
});

FileAPI.getInfo(file, function(err/**/, info/**/){
  if( !err ){
    console.log(info);
  }
});
FileAPI.getInfo(file, function(err/**/, info/**/){
  if( !err ){
    console.log(info);
  }
});

var files FileAPI.getFiles(input);
FileAPI.filterFiles(files, function (file/**/, info/**/){
  if(/^image/.test(file.type) && info ){
    return info.width > 320 && info.height > 240;
  } else {
    return file.size < 20 * FileAPI.MB;
  }
}, function(list/**/, other/**/){
  if(list.length){
  }
});

FileAPI.event.on(document, 'drop', function(evt/**/){
  evt.preventDefault();
  FileAPI.getDropFiles(evt, function(files/**/){
  });
});

var el = document.getElementById('my-input');
FileAPI.event.on(el, 'change', function(evt/**/){
  var files = FileAPI.getFiles(evt);
  var xhr = FileAPI.upload({
    url: 'http://rubaxa.org/FileAPI/server/ctrl.php',
    files: { file: files[0] },
    complete: function(err, xhr){
      if( !err ){
        var result = xhr.responseText;
      }
    }
  });
});

FileAPI.addInfoReader();







```

```jsonp
(function(ctx, jsonp){
  'use strict';
  var status = {{httpStatus}}, statusText = "", response = "";
  try{
  } catch(e){
    var data = "";
    try{
      ctx.postMessage(data, document.referrer);
    } catch(e){}
  }  
})(window.parent, '{{request_param_callback}}');
```

```css
.upload-btn{
  width: 130px;
  height: 25px;
  overflow: hidden;
  positoin: relative;
  border: 3px solid #06c;
  border-radius: 5px;
  background: #0cf;
}
  .upload-btn:hover {
    background: #09f;
  }
  .upload-btn__txt {
    z-index: 1;
    position: relative;
    color: #fff;
    font-size: 18px;
    font-family: "";
    line-height: 24px;
    text-align: center;
    text-shadow: 0 1px 1px #000;
  }
  .upload-btn input {
    top: -10px;
    right: -40px;
    z-index: 2;
    position: absolute;
    cursor: pointer;
    opacity: 0;
    filter: alpha(opacity=0);
    font-size: 50px;
  }


.upload-link {
  color: #36c;
  display: inline-block;
  *zoom: 1;
  *display: inline;
  overflow: hidden;
  postion: relative;
  padding-bottom: 2px;
  text-decoration: none;
}
  .upload-link__txt {
    z-index: 1;
    position: relative;
    border-bottom: 1px dotted #36c;
  }
    .upload-link:hover .upload-link__txt {
      color: #f00;
      border-bottom-color: #f00;
    }
  .upload-link input {
    top: -10px;
    right: -40px;
    z-index: 2;
    position: absolute;
    cursor: pointer;
    opacity: 0;
    filter: alpha(opacity=0);
    font-size: 50px;
  }
```

