# nginxWebUI 

修改版， 

修改点： 

一： 反向代理(server) 页面，域名链接支持 非标端口。

`/src/main/resources/WEB-INF/view/adminPage/server/index.html`

二：续签时间改为 下午14:35
`src/main/java/com/cym/task/ScheduleTask.java`   83行
// 续签证书
@Scheduled(cron = "0 0 2 * * ?")   改为
@Scheduled(cron = "35 0 14 * * ?")
页面文字

`/src/main/resources/messages.properties`  
101行
certStr.tips         = Automatic renewal will take place at 14:35 and certificates longer than 50 days will be renewed
`/src/main/resources/messages_en_US.properties`  101行
certStr.tips         = Automatic renewal will take place at 14:35 and certificates longer than 50 days will be renewed


### 修改原因

第一问题 是非标端口的时候，页面链接无法直接点开，给作者issues一直没回复，群里给他说了一下 答 `这个界面是展示信息用，不是给你高强度使用的` 

第二个修改时间，是为了避开高峰期 所以自己修改一下。

其他使用方法参考原作者，docker替换方法 `nginxwebui` 是容器名称

```
docker exec -it nginxwebui /bin/sh
rm /home/nginxWebUI.jar
exit # 退出容器
docker cp nginxWebUI.jar nginxwebui:/home/nginxWebUI.jar
```

## 下载地址
https://www.123pan.com/s/EqorVv-n0nPA  提取码:yhjt
