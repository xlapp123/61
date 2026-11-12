# Healing Pocket - 治愈系AI小手机

## 本次修复与更新内容
1. **清理环境残留与界面错位**：移除了预览环境注入的残余 WebSocket 拦截脚本与占位状态，修复了首次打开默认直接停留在设置页而非主桌面的问题。
2. **NovelAI 多站点与 V4.5 Full 兼容修复**：
   - 支持自定义官方与第三方站点 URL / Key，兼容 `/ai/generate-image`、根域名自动补全及 `/v1/images/generations` 协议。
   - 新增 `NAI Diffusion V4.5 Full`（`nai-diffusion-4-5-full`），支持 ZIP 压缩包自动解压、二进制流直读及 JSON Base64/URL 解析。
3. **微信上下文索要照片双保险闭环**：
   - 若对话模型未输出 `<nai:...>` 标签但检测到用户正在索要照片/自拍，会自动触发上下文英文提示词提取并调用 NovelAI 绘图；生成图片自动轻量压缩防止 `localStorage` 超限崩溃，点击图片可正常大图预览。
