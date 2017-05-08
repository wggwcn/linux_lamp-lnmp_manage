# linux_lamp-lnmp_manage

auto install apach/nginx php ftp    面板由：www.bt.cn 团队开发

---
1 install lamp_lnmp manager<br>
<code>yum install -y wget && wget -O install.sh http://download.bt.cn/install/install.sh && sh install.sh </code><br>

面板包含软件：
<ul style="margin-left:0"><li>Nginx-Tengine-2.2.0</li><li>Nginx1.8 - 1.10</li><li>Apache2.4.20</li><li>PHP5.2 - 7.1（安装时可选，支持多版本共存,除php7.0,php7.1都已包含zendloader）</li><li>MySQL5.5 - 5.7（安装时可选）</li><li>Pure-Ftpd</li><li>phpMyadmin</li><li>WEB在线面板
</li></ul>

面板管理常用命令：
----
停止<br>
<code>service bt stop </code><br>

启动 <br>
<code>service bt start </code><br> 

重启 <br>
<code>service bt restart </code><br>

卸载4.x面板<br>
<code>service bt stop && chkconfig --del bt && rm -f /etc/init.d/bt && rm -rf /www/server/panel </code><br> 
查看当前面板端口
<code>cat /www/server/panel/data/port.pl </code><br>

命令行修改面板端口，如要改成8881（centos 6）<br>
<code>echo '8881' > /www/server/panel/data/port.pl && service bt restart  </code><br>
<code>iptables -I INPUT -p tcp -m state --state NEW -m tcp --dport 8881 -j ACCEPT </code><br>

命令行修改面板端口，如要改成8881（centos 7）<br>
<code>echo '8881' > /www/server/panel/data/port.pl && service bt restart  </code><br>
<code>firewall-cmd --permanent --zone=public --add-port=8881/tcp </code><br>

强制修改MySQL管理(root)密码，如要改成123456<br>
<code>cd /www/server/panel && python tools.pyc root 123456 </code><br>

命令行修改面板密码，如要改成123456<br>
<code>cd /www/server/panel && python tools.pyc panel 123456 </code><br>

站点配置文件位置<br>
<code>/www/server/panel/vhost </code><br>

删除面板域名绑定<br>

<code>rm -f /www/server/panel/data/domain.conf </code><br>
清理登陆限制<br>

<code>rm -f /www/server/panel/data/*.login </code><br>
php.ini位置,如php5.4的<br>
</code>/www/server/php/54/etc/php.ini </code><br>

my.cnf位置<br>
<code>/etc/my.cnf </code><br>


<br>面板特色功能：
<ul style="margin-left:0">
<li>一键配置服务器环境（LANP/LNMP）</li>
<li>一键安全重启</li>
<li>一键创建管理网站、ftp、数据库</li>
<li>一键配置（定期备份、数据导入、伪静态、301、SSL、子目录、反向代理、切换PHP版本）</li>
<li>一键安装常用PHP扩展(fileinfo、intl、opcache、imap、memcache、apc、redis、ioncube、imagick)</li>
<li>数据库一键导入导出</li>
<li>系统监控（CPU、内存、磁盘IO、网络IO）</li>
<li>防火墙端口放行</li>
<li>SSH开启与关闭及SSH端口更改</li>
<li>禁PING开启或关闭</li>
<li>方便高效的文件管理器（上传、下载、压缩、解压、查看、编辑等等）</li>
<li>计划任务（定期备份、日志切割、shell脚本）</li>
<li>软件管理（一键安装、卸载、版本切换）</li>
</ul>
<br>
更新内容：
<ul class="litype_1" style="margin-left:0" type="1">
<li>全新UI</li>
<li>增加Nginx lua-waf模块(需重装Nginx方可使用)</li>
<li>增加mariadb10.0/10.1</li>
<li>增加MySQL配置文件自动修复功能</li>
<li>修正数据库备份脚本</li>
<li>重写软件管理模块</li>
<li>其它细节更新</li>
</ul>
<p><a href="http://www.bt.cn"><img src="https://www.bt.cn/Public/images/linux_pc.png" alt="ScrollReveal Demo" data-canonical-src="" style="max-width:100%;"></a></p>




<p><a href="http://www.bt.cn"><img src="http://www.bt.cn/bbs/newsimg/pic4.png" alt="ScrollReveal Demo" data-canonical-src="" style="max-width:100%;"></a></p>




