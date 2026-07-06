# HLS-Web-Player
- A self-hosted offline HLS monitor player for MediaMTX, featuring real-time bitrate stats via MediaMTX API, automatic buffer error recovery, shareable streaming links and full LAN offline support.
- 适配MediaMTX的内网HLS监控网页播放器
- 内置MTX API实时入流码率、分辨率显示、自动缓冲容错、一键分享链接、运行日志，完美兼容OBS SRT推流。

## 功能特性
- 纯静态HTML，仅需托管在简易http服务器或本地运行
- 离线内置 hls.min.js，无外网CDN依赖，局域网断网可用
- 实时视频分辨率监控
- 自动容错机制：Buffer阻塞、分片加载失败自动重试恢复
- URL传参分享链接，手机/电脑一键打开直接播放，例：http://x.x.x.x/player.html?stream=http://x.x.x.x:8888/live/index.m3u8
- 完整运行日志，限制日志条数防内存溢出
- 防重复播放、资源自动销毁、定时器清理
- 全平台兼容：Windows Edge/Firefox、安卓浏览器、iPhone Safari
- 使用OBS串流测试，无音频无声问题

## 环境要求
1. MediaMTX >= 1.19.2
2. OBS Studio（SRT推流）
3. 内网环境，服务器开放端口：
   - 8888：HLS流媒体 + 静态网页服务
   - 8890：SRT推流UDP端口

## 快速部署
### 1. MediaMTX 配置
将仓库内 `mediamtx.yml.example` 复制重命名为 `mediamtx.yml`
关键配置说明：
- 开启API跨域，用于读取分辨率
- SRT、HLS跨域全部放行局域网访问

# AI开发辅助说明
- 本项目完整播放器页面、实时码率API逻辑、分片缓冲自动重试容错、URL分享功能均由豆包AI辅助生成；
- 全部代码经过人工修改、测试、适配MediaMTX 1.19.2，修复兼容性bug，所有业务逻辑由人工把控。
