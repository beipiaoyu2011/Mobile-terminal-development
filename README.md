# Mobile-terminal-development
前端开发-手机端和pc端显示文字不同的问题
在响应式页面的时候，在手机显示的时候，要有文字显示“长按关注”，在pc上面显示文字为“请扫描关注”，能否适应不同屏幕，出现不同文字


判断客户端类型
var client = {
  versions: function() {
    var u = navigator.userAgent;
    return {
      ios: !!u.match(/\(i[^;]+;( U;)? CPU.+Mac OS X/), //ios终端  
      android: u.indexOf('Android') > -1 || u.indexOf('Linux') > -1, //android终端或者uc浏览器  
    }
  }()
}

//get value 
var btnvalue = document.getElementById('btn').innerText;
console.log(btnvalue);

if (client.versions.ios) {
  console.log("ios");
  document.getElementById('btn').innerHTML = 'ios client';
} else if (client.versions.android) {
  console.log("andriod");
  document.getElementById('btn').innerHTML = 'andriod client';
} else {

  document.getElementById('btn').innerHTML = 'PC client';
  console.log("不是移动设备");
}
