```php
<?php
/**
 * Created by PhpStorm.
 * User: 304455977@qq.com
 * Date: 2017/9/30
 * Time: 10:03
 */

namespace app\logic;

use Alidayu;


class Message
{



    /**
     * 阿里大鱼发送短信
     */
    public function senddayuMessage($status,$params=[]){
  
        $message=new Alidayu();

        switch($status){
            case 1;
                $number="SMS_165000248";//用户注册验证码
                break;
             case 2;
                 $number="SMS_165000247";//用户注册验证码
                 break;
             case 3;
                 $number="SMS_165109746";//任务通知短信
        }

        $send_content=[
            "code"=>$params["code"],
            "prodcut"=>$params["code"]
        ];

        $params=[
            "phone"=>$params["mobile"],
            "number"=>$number,
            "send_content"=>$send_content
        ];
        $res=$message->sendSms($params);

        return $res;
    }



}
```
