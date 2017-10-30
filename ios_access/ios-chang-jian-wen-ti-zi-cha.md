#iOS常见问题自查

问：初始化信鸽接口，出现如下日志
2017-10-26 15:13:38.888951+0800 XG-Demo[2295:1737660] [xgpush] 服务器返回码: 20
答：在初始化信鸽的方法中 appid和appkey不要使用宏定义


答：每小时最多可创建30条全量推送，超过30条的推送将被推送暂停
一小时内创建推送内容完全一样的推送，将被推送暂停
推送暂停的任务将不会下发，请视情况重新创建推送



a）验证失败，请刷新后重试
b）不包含push参数
c）文件大小为0kb，不能上传
信鸽证书制作教程：https://v.qq.com/x/page/u0302fjna1h.html

问：终端出现"Error Domain=NSCocoaErrorDomain Code=3000 "未找到应用程序的“aps-environment”的授权字符串" UserInfo=0x16545fc0 {NSLocalizedDescription=未找到应用程序的“aps-environment”的授权字符串}"错误
答：这是由于app证书没有推送权限引起的.请重新配置证书


答：iOS10会进静默通知的回调方法中

问：设置/删除标签的时候出现如下错误
答：请在registerDevice之后再setTag/delTag.在registerDevice之前进行tag操作会出现这个错误

问：token和别名（account）的对应关系
答：一个设备一个token，token在注册推送时由苹果下发，一个token最多绑定一个account，一个account最多绑定15个token，超出数量时会顶替之前绑定的token。iOS的token是会变化的，卸载，重装，刷机，重置都会导致token发生变化。

问：使用信鸽服务端sdk，怎么创建静默推送
