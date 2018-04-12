# music

> vue

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).


/*本音乐播放器是基于audio标签开发，不支持audio标签标准API的浏览器可能无法正常播放音乐，

1，本播放器提供了歌曲暂停功能，播放功能，自动下一曲功能，歌曲总时间功能，当前播放时间功能，歌曲循环功能。。。

2，使用方法！！！，在父组件引入改音乐播放的子组件，通过父组件传递歌曲路径的数组列表即可播放，

使用方法可参考下面注释代码，

initvolume代表音量的初始值，不传默认为30%；改变默认参数可在父组件的data中定义,例(volume:0.6)

@time表示播放器传递出来的音乐的进度以及总时长的对象，里面总共有四个属性，currenttime（代表格式化后的当前播放时间，如3:02），

alltime（代表格式化后的歌曲总共时长，如5:02），totaltimemm（代表未格式化的歌曲总共时长，如110s），currenttimemm（代表未格式化的歌曲当前进度，如210s）
获取对象的属性可在父组件methods方法中使用time事件获取，

父组件可操作该播放器的方法：
！！！ this.$refs.child.novoice() // 是否静音，父组件中调用一次静音，再次调用恢复正常音量
！！！this.$refs.child.last()  // 播放与暂停方法，同上。
！！！this.$refs.child.loop()  // 同上
！！！this.$refs.child.next()  // 调用后播放下一曲
！！！this.$refs.child.last()  // 调用后播放上一曲
！！！this.$refs.child.$emit('volume',this.sound) // 改变播放器音量的方法，事件名必须为volume，this.sound代表父组件传递进子组件的音量，取值为0-1,。
！！！this.$refs.child.$emit('range',this.ranges) // 改变播放器播放进度的方法，事件名必须为range，this.ranges代表父组件传递进子组件的进度，取值范围为0到@time事件的属性totaltimemm之间的数值

//  <music-box ref='child'    @time='time' :musiclist='musicsrc' :initvolume='volume'></music-box>
// import MusicBox from './music.vue'
// export default {
//     components:{
// MusicBox
//     },

*/ 