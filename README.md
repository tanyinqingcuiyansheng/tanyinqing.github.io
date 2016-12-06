# tanyinqing.github.io

浏览器查看数据的连接
* [1. 生成新订单](#1)
* [2. 生成付款密钥](#2)


<h5 id="1">1. 生成新订单的连接<h5>
```
这个是服务器的地址订单
http://211.149.169.221:8080/umijoyappsvr/order/createOrder.do?goodsIds=24989N1C24536N1&user.id=479&deliveryAddress.id=449&payMethod.id=12&discountCode=fghhgfhgfh&remark=%E4%B8%8D%E7%94%A8%E9%85%8D%E9%80%81&storeId=28&storeName=%E5%98%89%E6%9F%8F%E5%B0%8F%E5%8C%BA
测试服务器的地址
http://192.168.10.192:8080/umijoyappsvr/order/createOrder.do?goodsIds=24989N1C24536N1&user.id=479&deliveryAddress.id=449&payMethod.id=12&discountCode=fghhgfhgfh&remark=%E4%B8%8D%E7%94%A8%E9%85%8D%E9%80%81&storeId=28&storeName=%E5%98%89%E6%9F%8F%E5%B0%8F%E5%8C%BA
```  
<h5 id="2">2. 生成付款密钥<h5>

`
这是激光推送定义的广播
<!-- User defined.  For test only  用户自定义的广播接收器 -->
        <receiver
            android:name=".activity.jpush.MyReceiver"
            android:enabled="true"
            android:exported="false" >
            <intent-filter>
                <action android:name="cn.jpush.android.intent.REGISTRATION" /> <!-- Required  用户注册SDK的intent -->
                <action android:name="cn.jpush.android.intent.UNREGISTRATION" />
                <action android:name="cn.jpush.android.intent.MESSAGE_RECEIVED" /> <!-- Required  用户接收SDK消息的intent -->
                <action android:name="cn.jpush.android.intent.NOTIFICATION_RECEIVED" /> <!-- Required  用户接收SDK通知栏信息的intent -->
                <action android:name="cn.jpush.android.intent.NOTIFICATION_OPENED" /> <!-- Required  用户打开自定义通知栏的intent -->
                <action android:name="cn.jpush.android.intent.ACTION_RICHPUSH_CALLBACK" /> <!-- Optional 用户接受Rich Push Javascript 回调函数的intent -->
                <action android:name="cn.jpush.android.intent.CONNECTION" /> <!-- 接收网络变化 连接/断开 since 1.6.3 -->
                <category android:name="com.linyou.lifedelivery" />
            </intent-filter>
        </receiver>
        
        
        发送广播的代码
        Intent mIntent=new Intent();
       mIntent.setAction("cn.jpush.android.intent.NOTIFICATION_OPENED");
   Bundle mBundle=new Bundle();
      mBundle.putString("msg", "停止音乐");
         mIntent.putExtras(mBundle);
       mContext.sendBroadcast(mIntent);
     // Log.d("JPush", "发送了抢单的通知");
```
<h5 id="4">4. 区域别名的设置<h5/>  
