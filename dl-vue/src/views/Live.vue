<template>
  <div class="hello-ezuikit-js"  style="position:absolute;left:50%;top:50%;transform: translate(-50%,-50%);">
    <div id="video-container" style="width:600px; height:600px;align:center;"></div>
  </div>
</template>

<script>
import EZUIKit from "ezuikit-js";

export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  mounted: () => {
    console.group("mounted 组件挂载完毕状态===============》");
    var player = new EZUIKit.EZUIKitPlayer({
      autoplay: true,
      id: "video-container",
      accessToken:
        "at.a0gfypns5jk0wcwv4p4rqjpa538npovs-1ou3m82qil-0mvrllv-5nhgyyqmx",
      url: "ezopen://open.ys7.com/F85471438/1.live",
      template: "standard", // simple - 极简版;standard-标准版;security - 安防版(预览回放);voice-语音版；
      // 视频上方头部控件
      //header: ["capturePicture", "save", "zoom"], // 如果templete参数不为simple,该字段将被覆盖
      //plugin: ['talk'],                       // 加载插件，talk-对讲
      // 视频下方底部控件
      // footer: ["talk", "broadcast", "hd", "fullScreen"], // 如果template参数不为simple,该字段将被覆盖
      // audio: 1, // 是否默认开启声音 0 - 关闭 1 - 开启
      // openSoundCallBack: data => console.log("开启声音回调", data),
      // closeSoundCallBack: data => console.log("关闭声音回调", data),
      // startSaveCallBack: data => console.log("开始录像回调", data),
      // stopSaveCallBack: data => console.log("录像回调", data),
      // capturePictureCallBack: data => console.log("截图成功回调", data),
      // fullScreenCallBack: data => console.log("全屏回调", data),
      // getOSDTimeCallBack: data => console.log("获取OSDTime回调", data),
      width: 600,
      height: 400,
    });
    console.log("player", player);
    setTimeout(() => {
      player.stop(); // 方法调用示例，10秒后关闭视频
    }, 20000);
  },
};
</script>