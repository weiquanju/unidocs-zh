## audio
音频。

**平台差异说明**

|App|HarmonyOS Next|Web|微信小程序|支付宝小程序|百度小程序|抖音小程序、飞书小程序|QQ小程序|快手小程序|京东小程序|元服务|小红书小程序|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|√|x|√|√|x|√|x|x|x|x|x|x|

**注意：** 微信小程序平台自基础库 1.6.0 版本开始，不再维护 audio 组件，推荐使用API方式而不是组件方式来播放音频。API见 [uni.createInnerAudioContext](/api/media/audio-context?id=createinneraudiocontext) 替代。

app-nvue也不支持此组件。

如果需要带ui的样式，可以自己做，也可以在插件市场搜索相关[插件](https://ext.dcloud.net.cn/search?q=audio)

本组件在vue3项目中废弃，只可以在vue2项目中使用

**属性说明**

|属性名|类型|默认值|说明|
|:-|:-|:-|:-|
|id|String||audio 组件的唯一标识符|
|src|String||要播放音频的资源地址|
|loop|Boolean|false|是否循环播放|
|controls|Boolean|false|是否显示默认控件|
|poster|String||默认控件上的音频封面的图片资源地址，如果 controls 属性值为 false 则设置 poster 无效|
|name|String|未知音频|默认控件上的音频名字，如果 controls 属性值为 false 则设置 name 无效|
|author|String|未知作者|默认控件上的作者名字，如果 controls 属性值为 false 则设置 author 无效|
|@error|EventHandle||当发生错误时触发 error 事件，detail = {errMsg: string, errCode: number}|
|@play|EventHandle||当开始/继续播放时触发play事件|
|@pause|EventHandle||当暂停播放时触发 pause 事件|
|@timeupdate|EventHandle||当播放进度改变时触发 timeupdate 事件，detail = {currentTime, duration}|
|@ended|EventHandle||当播放到末尾时触发 ended 事件|

**MediaError.code**

|返回错误码|描述|
|:-|:-|
|1|获取资源被用户禁止|
|2|网络错误|
|3|解码错误|
|4|不合适资源|

**示例：** [查看示例](https://hellouniapp.dcloud.net.cn/pages/component/audio/audio)

```html
<template>
	<view>
		<view class="page-body">
			<view class="page-section page-section-gap" style="text-align: center;">
				<audio style="text-align: left" :src="current.src" :poster="current.poster" :name="current.name" :author="current.author" :action="audioAction" controls></audio>
			</view>
		</view>
	</view>
</template>
```


```javascript
export default {
	data() {
		return {
			current: {
				poster: 'https://qiniu-web-assets.dcloud.net.cn/unidoc/zh/music-a.png',
				name: '致爱丽丝',
				author: '暂无',
				src: 'https://web-ext-storage.dcloud.net.cn/uni-app/ForElise.mp3',
			},
			audioAction: {
				method: 'pause'
			}
		}
	}
}
```

![uniapp](https://qiniu-web-assets.dcloud.net.cn/unidoc/zh/audio.png)
