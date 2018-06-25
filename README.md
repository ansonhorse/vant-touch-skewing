# vant180625

一个挺奇怪的问题！

暂时只在Android的Google Chrome上发现。

> 在某种情况下，绝对定位的元素触摸不到，详细点说，就是在视觉上是触摸这个元素，但实际上是触摸到了另一个地方。

至于这个"某种情况"，暂时没有确定，也就是这个问题的重现方式我暂时也说不定。这个大致给一些操作逻辑，但不确保可以触发：
1. 快速滑动到底部，再向上滑动一段距离；
2. 随意上下滑动；
3. 在滑动之前附带一些随机触摸操作；

[查看视频](https://github.com/ansonhorse/vant-touch-skewing/raw/master/screenshots/2018-06-25_12_02_54.mp4)

### 2018-06-25 15:27:11 更新：
> 做了一个纯粹的示例，发现也有这个问题，看来这个应该是Chrome本身的bug。

[不引用vant或者其他任何UI库的测试示例](https://github.com/ansonhorse/vant-touch-skewing/raw/master/screenshots/plain.mp4)


``` bash
# 1. 按需修改开发模式访问的ip和port，以让手机可以访问
config.dev.host
config.dev.port

# 2. run
npm run dev

# 3. 访问 http://你的ip:port/#/test
```
