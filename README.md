## Lumia950XL win10arm项目主题网/cnLeeLin/vesion：beta20190517

<a href="https://www.bilibili.com/video/av51168084/">演示视频</a>
<h3>讨论QQ群：129348124</h3>
<h3>目前笔者设备只有lumia950xl 所以以950xl为主 之后如果入手950和rx-130会相对应更新</h3>
<a href="https://github.com/WOA-Project/MSM8994-8992-NT-ARM64-Drivers">以下大部分内容来自github WOA项目(点击可进入源地址)</a>
<a href="https://github.com/ADeltaX/MobileShell/releases/tag/r709">触屏优化类似WP菜单MoblieShell</a>
<h4>特征	细节	工作状态
WLAN	WiFi 2.4Ghz和5Ghz	工作/
触摸	最多5个手指，右键单击支持	工作/
全球定位系统	首次运行时需要互联网连接才能下载地图数据	工作/
Miracast时	接收内容，投影内容可能无法与某些OEM笔记本电脑和移动设备上的接收器配合使用	工作/
蓝牙	Windows问题可能会发生随机断开	工作/
NFC	读，写	工作/
SD卡插槽		工作/
eMMC	包括三星在内的所有品牌均以HS400速度运行	工作/
电池	充电，读数	工作
侧按钮	音量控制，锁定/解锁/关闭电源，相机	工作/
已连接待机	S0网络连接状态	工作/
SoC核心	全部8个核心	工作/
显示屏	亮度控制，色彩准确	工作/
细胞的	适用于所有支持频段，双SIM卡设备的数据，文本和呼叫可能存在APN问题	工作/
GPU	ARM64，ARM32 Direct X部分支持	部分工作/
音频	扬声器音量锁定为100％，某些输出频率无法播放	部分工作/
USB C	需要在注册表中手动VBus启用电源输出，不会自动检测插头插入	部分工作/
HDMI输出	需要USB C才能工作	不工作/
传感器	陀螺仪，加速度计，环境光传感器	不工作/
相机	缺少驱动	不工作/
虹膜扫描仪	缺少驱动	不工作/
振动电机		不工作/
调频收音机		不工作/h4>
    
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

