#Make DUOSHUO Show UA
> �汾��0.1<br>
> ������http://jibushengdan.tk/make_duoshuo_show_ua.jbsd

##���
> ������˼��ʹ��˵������ʾua<br>
> �����20��<br>
> �ô�������ua-parser����ua����ַ��https://github.com/faisalman/ua-parser-js

##ʹ��
> ��test.html<br>
> ���Զ�����ʾ��ɫcss���.this_ua.platform.������ƣ�ע���Сд��

##����
> �����֪�������´�����ںδ�����Կ��Ƿ������½ڵ�ĩβ

		<script type="text/javascript">
		if (typeof DUOSHUO !== 'undefined')hookDUOSHUO_tp();
		else $('[src="http://static.duoshuo.com/embed.js"]')[0].onload=hookDUOSHUO_tp;
		function hookDUOSHUO_tp(){
			var _D_post=DUOSHUO.templates.post
			DUOSHUO.templates.post=function (e,t){
				var rs=_D_post(e,t);
				if(e.agent&&/^Mozilla/.test(e.agent))rs=rs.replace(/<\/div><p>/,show_ua(e.agent)+'</div><p>');
				return rs;
			}
		}
		function show_ua(string){
			console.log(string)
			$.ua.set(string);
			var sua=$.ua;
			if(sua.os.version=='x86_64')sua.os.version='x64';
			return '<span class="this_ua platform '+sua.os.name+'">'+sua.os.name+' '+sua.os.version+'</span><span class="this_ua browser '+sua.browser.name+'">'+sua.browser.name+'|'+sua.browser.version+'</span>';
		}
		</script>