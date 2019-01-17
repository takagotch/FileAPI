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

FileAPI.addInfoReader(/^image/, function (file/**/, callback/**/){
  FileAPI.readAsBinaryString(file, function(evt/**/){
    if( evt.type == 'load' ){
      var binaryString = evt.result;
      var oFile = new BinaryFile(binaryString, 0, file.size);
      var exif = EXIF.readFromBinaryFile(oFile);
      callback(false, { 'exif': exif || {} });
    }
    else if( evt.type == 'error' ){
      callback('read_as_binary_string');
    }
    else if( evt.type == 'progress' ){
    }
  });
});

FileAPI.readAsDataURL(file, function(evt/**/){
  if(evt.type == 'load' ){
    var dataURL = evt.result;
  } else if( evt.type =='progress' ){
    var pr = evt.loaded/evt.total * 100;
  } else {
  }
})

FileAPI.readAsBinaryString(file, function(evt/**/){
  if( evt.type == 'load' ){
    var binaryString = evt.result;
  } else if(evt.type == 'progress'){
    var pr = evt.loaded/evt.total * 100;
  }
})

FileAPI.readAsArrayBuffer(file, function(evt/**/){
  if( evt.type == 'load' ){
    var arrayBuffer = evt.result;
  } else if(evt.type == 'progress' ){
    var pr = evt.loaded/evt.total * 100;
  } else {
  }
})

FileAPI.readAsText(file, function(evt/**/){
  if( evt.type == 'load' ){
    var text = evt.result;
  } else if( evt.type == 'progress' ){
    var pr = evt.loaded/evt.total * 100;
  } else {
  }
})

FileAPI.readAsText(file, "utf-8", function(evt/**/){
  if( evt.type == 'load' ){
    var text = evt.result;
  } else if( evt.type == 'progress' ){
    var pr = evt.loaded/evt.total * 100;
  }
})

var xhr = FileAPI.upload({
  url: '',
  data: { 'session-id': 123 },
  files: {},
});

var xhr = FileAPI.upload({
  url: '...',
  data: { 'x-upload': 'fileapi' },
  files: {},
});

var xhr = FileAPI.upload({
  url: '',
  files: {
    audio: files
  }
});

var xhr = FileAPI.upload({
  url: '',
  files: { images: fileList },
  chunkSize: 0.5 * FileAPI.MB
});

var xhr = FileAPI.upload({
  url: '',
  files: { images: fileList },
  chunkSize: 0.5 * FileAPI.MB,
  chunkUploadRetry: 3
});

var xhr = FileAPI.upload({
 url: '',
 files: { image: imageFiles },
 imageTransform: {
   maxWidth: 800,
   maxHeight: 600,
   overlay: [{ x: 10, y: 10, src: '/i/watemark.png', rel: FileAPI.Image.RIGHT_BOTTOM }]
 }
});

var xhr = FileAPI.upload({
  url: '',
  files: { image: imageFiles },
  imageTransform: {
    'huge': { maxWidth: 800, maxHeight: 600 },
    'medium': { width: 320, height: 240, preview: true },
    'small': {
      width: 100, height: 100,
      overlay: [{ x: 5, y: 5, src: '/i/watermark.png', rel: FileAPI.Image.RIGHT_BOTTOM}]
    }
  }
});

var xhr = FileAPI.upload({
 url: '',
 files: { image: imageFiles },
 imageTransform: {
   type: 'image/jpeg',
   quality: 0.86
 }
});

var xhr = FileAPI.upload({
  url: '',
  files: {}
  prepare: function(file/**/, options/**/){
    options.data.secret = utils.getSecretKey(file.name);
  }
});

var xhr = FileAPI.uplaod({
  url: '',
  files: {}
  upload: function(xhr/**/, options/**/){
  }
});

var xhr = FileAPI.upload({
  url: '',
  files: {}
  upload: function(file/**/, xhr/**/, options/**/){
  }
});

var xhr = FileAPI.upload({
  url: '',
  files: {}
  progress: function(evt/**/, file/**/, options/**/){
    var pr = evt.loaded/evt.total * 100;
  }
});

var xhr = FileAPI.upload({
  url: '',
  files: {}
  fileprogress: function(evt/**/, file/**/, xhr/**/, options/**/){
    var pr = evt.loaded/evt.total * 100;
  }
});

var xhr = FileAPI.upload({
  url: '',
  files: {}
  complete: function(err/**/, xhr/**/, file/**/, options/**/){
    if( !err ){
    }
  }
});

var xhr = FileAPI.upload({
  url: '',
  files: {}
  filecomplete: function(err/**/, xhr/**/, file/**/, options/**/){
    if( !err ){
      var result = xhr.responseText;
    }
  }
});

var el = document.getElementById('dropzone');
FileAPI.event.dnd(el, function(over){
  el.style.backgroundColor = over ? '': '';
}, function(files){
  if(files.length){
  }
});
$('#dropzone').dnd(hoverFn, dropFn)

FileAPI.event.dnd.off(el, hoverFn, dropFn)
$('#dropzone').dndoff(hoverFn, dropFn)

FileAPI.Image(imageFile).get(function(err/**/, img/**/){
  if( !err ){
    document.body.appendChild( img );
  }
});

FileAPI.Image(iamgeFile)
  .crop(640, 480)
  .get(function(err/**/, img/**/){
  
  })
;

FileAPI.Image(imageFile)
  .crop(100, 50, 320, 240)
  .get(function(err/**/, img/**/){
  
  })
;

FileAPI.Image(imageFile)
  .resize(320, 240)
  .get(function(err/**/, img/**/){
  
  })
;

FileAPI.Image(imageFile)
  .resize(320, 240, 'max')
  .get(function(err/**/, img/**/){
  
  })
;
FileAPI.Image(imgeFile)
  .resize(240, 'height')
  .get(function(err/**/, img/**/){
  
  })
;

FileAPI.Image(imageFile)
  .preview(100, 100)
  .get(funcion(err/**/, img/**/){
  
  })
;

FileAPI.Image(imageFile)
  .rotate(90)
  .get(function(err/**/, img/**/){
  
  })
;

FileAPI.Image(imageFile)
  .filter(function(canvas/**/, doneFn/**/){
    doneFn();
  })
  .get(function(err/**/, img/**/){
  
  })
;

Caman.Filter.register("my-funky-filter", function(){
});
FileAPI.Image(imageFile)
  .filter("my-funky-filter")
  .get(function(err/**/, img/**/){
  
  })
;

FileAPI.Image(imageFile)
  .overlay({
    { x: 10, y: 10, w: 100, h: 10, src: '/i/watermark.png' },
    { x: 10, y: 10, src: '/i/watermark.png', rel: FileAPI.Image.RIGHT_BOTTOM }
  })
  .get(function(err/**/, img/**/){
  
  })
;

var el = document.getElementById('cam');
FileAPI.Camera.publish(el, {width: 320, height: 240 }, function(err, cam/**/){
  if( !err ){
  }
});

var el = document.getElementById('cam');
FileAPI.Camera.publish(el, { start: false }, function(err, cam/**/){
  if( !err ){
    cam.start(function(err){
      if( !err ){
      }
    });
  }
});

var el = document.getElementById('cam');
FileAPI.Camera.publish(el, function(err, cam/**/){
  if( !err ){
    var shot = cam.shot();
    shot.preview(100).get(function(err, img){
      previews.appendChild(img);
    });
    FileAPI.upload({
      url: '',
      files: { cam: shot
    });
  }
});

var FileAPI = {
  staticPath: '/js/',
  flashUrl: '/statics/FileAPI.flash.swf',
  flashImageUrl: '/statics/FileAPI.flash.image.swf'
};

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

