## Lumia950XL win10arm项目主题网/cnLeeLin/vesion：beta20190517

<a href="https://www.bilibili.com/video/av51168084/">演示视频</a>
<h3>讨论QQ群：129348124</h3>
<h3>目前笔者设备只有lumia950xl 所以以950xl为主 之后如果入手950和rx-130会相对应更新</h3>
<a href="https://github.com/WOA-Project/MSM8994-8992-NT-ARM64-Drivers">以下大部分内容来自github WOA项目(点击可进入源地址)</a>
<a href="https://github.com/ADeltaX/MobileShell/releases/tag/r709">触屏优化类似WP菜单MoblieShell</a>

<h4>目前不支持驱动5/20：
虹膜生物识别传感器（缺少驱动程序）
相机（缺少驱动程序）
所有传感器（ALS除外）
扬声器的音量控制（卡在100％）
振动电机
通过USB-C输出HDMI
缺少x86 DirectX支持。
调频收音机/h4>
    
<h4>目前笔者自测发现的问题:支持32位和64位的uwp应用和32位的桌面应用(exe格式)，由于GPU驱动不完善所以对2D和3D应用/游戏会很卡或者死机，整体系统还算和uwp应用还是比较流畅的，底部cpu部位发热严重(骁龙810不是吹的)，耗电快，充电慢。5/20</h4>
<h4>目前手中两台rx-1085(950xl单卡欧版)GPS,听筒,外放，4G数据，通话，短信正常(使用woa2.5.5)。插入SIM卡后win10系统会自动下载拨号，短信，数据设置等APP，UI有很多BUG，但属于可用状态。5/27</h4>


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

