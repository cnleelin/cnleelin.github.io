## Lumia950XL win10arm项目中文网/cnLeeLin/vesion：beta20190517

<a href="https://www.bilibili.com/video/av51168084/">演示视频</a>
<h3>讨论QQ群：129348124</h3>
目前笔者设备只有lumia950xl 所以以950xl为主 之后如果入手950和rx-130会相对应更新
<a href="https://github.com/WOA-Project/MSM8994-8992-NT-ARM64-Drivers">以下大部分内容来自github WOA项目(点击可进入源地址)</a>



<h1>TEST 1</h1>
<h2>TEST 2</h2>
<h3>TEST 3</h3>
<h4>TEST 4</h4>
<h5>TEST 5</h5>
<h6>TEST 6</h6>


<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
    </head>
    <body>
        <h1>留言板无后台测试中，评论无效</h1>
        <textarea id="memo" cols="60" rows="10"></textarea>
        <input type="button" value="追加内容" onclick="saveStorage('memo')" />
        <input type="button" value="初始化" onclick="clearStorage('msg')" />
        <hr />
        <p id="msg"></p>
        <script type="text/javascript">

            function saveStorage(id) {
                //获取textarea的value值
                var data = document.getElementById(id).value;
                //获取当前时间戳
                var time = new Date().getTime();
                //将时间戳作为键值，textarea的value值作为键值的内容保存在本地数据库
                localStorage.setItem(time,data);
                //保存成功后提示成功
                console.log("数据已保存");
                //设置loadStorage函数的传参（ID值）
                loadStorage('msg');
            }

            function loadStorage(id) {
                var result = '<table border="1">';
                //遍历本地数据所有内容
                for(var i = 0; i < localStorage.length; i++) {
                    //获取每一条新增的键值
                    var kes = localStorage.key(i);
                    //获取新增键值的内容
                    var value = localStorage.getItem(kes);
                    //获取时间对象
                    var date = new Date();
                    //将时间戳转化为正常时间 Mon Jun 19 1972 11:12:44 GMT+0800 (中国标准时间) 的格式
                    date.setTime(kes);
                    //将转化后的内容变成字符串
                    var datestr = date.toGMTString();
                    //将所有新增内容添加到result变量中
                    result += '<tr><td>' + value + '</td><td>' + datestr + '</td></tr>'
                }
                result += '</table>';
                var target = document.getElementById(id);
                //将所有内容添加到元素中显示
                target.innerHTML = result;

            }

            function clearStorage() {
                //清除本地储存所有内容
                localStorage.clear();  
                console.log("清除完毕");
            }

        </script>
    </body>
</html>

