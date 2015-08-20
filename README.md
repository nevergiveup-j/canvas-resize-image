# 移动端上传图片
上传图片使用canvas 压缩图片不需要上传服务器展示图片

## 查看DEMO
[canvas-resize-image](http://nevergiveup-j.github.io/canvas-resize-image/)

## 例子
<pre><code>
$('#photo').resizeIMG({
  width: 200,
  quality: 0.8,
  successCallback: function(result){
      if(result.status === 200) {
          var img = new Image();
          
          img.src = result.data.base64;

          $('body').append(img);
      } else {
          alert(result.message);
      }
      
  }
});
</code></pre>

## 参数说明
#### $(elem) 上传按扭元素
<pre><code>
$(elem).resizeIMG(options);
</code></pre>

#### options <code>Object</code> 配置<br />
width <code>String</code> 图片需要压缩的宽度，高度会跟随调整<br />
quality <code>Number</code> 压缩质量，不压缩为1<br />
fileSize <code>Number</code> 图片大小 MB<br />
fileMessage <code>Number</code> 图片大小提示文字<br />
beforeCallback <code>Function</code> 处理前函数<br />
successCallback <code>Function</code> 成功回调

## 使用其它插件说明
### zepto.min.js
这个不用说了～

### exif.min.js
读取图像数据，使用图片拍照方向
<pre><code>
  EXIF.getTag(file, 'Orientation')
</code></pre>

### jpeg_encoder_basic.js 
修复android bug

### megapix-image.js 
修复IOS bug 
