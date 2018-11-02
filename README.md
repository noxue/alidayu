# alidayu
阿里大于最新sdk 2017-05-25

本sdk基于阿里大于java最新版，版本为2017-05-25  

因开发中需求短信发送，一开始没准备自己写，找了几个go版本的，发现怎么调用都会错，
后来在阿里的sdk中发现原来所有的都改变了，原sdk已经无法现使用，没办法，只好自己
封装。   

使用非常简单

> go get github.com/ying32/alidayu  

* 方法一：  

```golang 
import "github.com/ying32/alidayu"

func main() {
    result, _, err :=  alidayu.SendSMS("13333333333", "验证码", "你的模板id", "{\"number\": \"123456\"}", "你的 appKey", "你的 appSecret string")
    fmt.Println(result)
    fmt.Println(err)
}
```

* 方法二：  

```golang 
import "github.com/ying32/alidayu"

func main() {
    // 全局设置appKey与appSecret
    alidayu.AppKey = "你的 appKey"
    alidayu.AppSecret = "你的 appSecret"
    // 使用默认的发送
    result, _, err :=  alidayu.SendSMS2("13333333333", "验证码", "你的模板id", "{\"number\": \"123456\"}")
    fmt.Println(result)
    fmt.Println(err)
}
```