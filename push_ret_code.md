##服务端返回码

|值|含义|可采取措施|
|---|---|----|
|0|调用成功|
|-1|参数错误|检查参数配置|
|-2|请求时间戳不在有效期内|检查设备当前时间|
|-3|recv失败|稍后重试|
|-5|Action处理超时|稍后重试|
|2|非法参数|检查参数配置|
|5|与CMEM通讯失败|稍后重试（推送超时）|
|6|设备token未成功注册|请检查终端设备注册是否成功|
|7|通用错误，账号超限|删除其他未使用的账号(调用账号解绑）|
|14|token非法|Android Token长度为40位，iOS Token长度为64位|
|15|信鸽逻辑服务器繁忙|稍后重试|
|16|系统繁忙|稍后重试|
|19|操作时序错误。例如进行tag操作前未获取到deviceToken|没有获取到deviceToken的原因：1.没有注册信鸽或者苹果推送2.provisioning profile制作不正确|
|20|鉴权错误，可能是由于Access ID和Access Key不匹配|检查Access ID和Access Key（注意空格）|
|21|鉴权失败|检查Access ID和Access Key|
|40|推送的token没有在信鸽中注册|检查token是否注册|
|48|推送的账号没有绑定token|检查account和token是否有绑定关系见推送指南：绑定/设置账号见热门问题解答：账号和设备未绑定的解答|
|53|设备未注册|反注册后重新注册|
|73|消息字符数超限|iOS目前是1000字节左右，苹果的额外推送设置如角标，也会占用字节数|
|75|消息体格式不符合json格式|检查消息体即message字段内容|
|76|请求过于频繁，请稍后再试|全量广播限频为每3秒一次|
|78|循环任务参数错误|检查loop time|
|90|设备离线|重新打开应用|
|91|设备tag过多|清理不使用的tag|
|92|apptag过多|清理不使用的tag|
|100|APNS证书错误，请重新提交正确的证书|证书格式是pem的，另外，注意区分生产证书、开发证书的区别|
|-101|参数错误|请检查参数|
|-102|请求timestamp字段超过了时间过期|请使用当前系统时间戳，确保时间同步|
|-103|sign 不合法|检查签名生成流程，生成sign是METHOD 必须与请求时所使用的一致|
|-105|请求过于频繁|稍后重试|
|-106|证书错误|证书错误|
|-111|缺少公共参数：access_id\timestamp\sign|检查公共参数access_id\timestamp\sign|
|-112|参数取值非法|检查参数取值|
|其他|信鸽内部错误|稍后重试，如出现为标明且必现错误请及时与我们取得联系|


