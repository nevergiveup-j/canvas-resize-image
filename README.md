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
<pre><code>
$(elem).resizeIMG(options);
</code></pre>
