# Petvewi NFC public UI preview

GitHub Pages 静态 UI 预览，不需要电脑或本地 API 在线。

- 未丢失页：`https://goal1821.github.io/nfc/c.html`（首页、旧 `d.html` / `o.html` 同样显示头像与打开 App）。
- 丢失页设计演示：`https://goal1821.github.io/nfc/lost.html`。姓名、品种、联系电话均为明确标注的虚构测试资料，不是实际丢失事件，也不是账号联系方式；测试号码不可拨打。
- `pet-avatar.jpg` 是账号主人授权用于本次公开 UI 的 App 上传头像快照，不再使用示例猫狗照片。不会自动同步后续头像变更。

未丢失页面的 HTML 中也不包含联系人、电话或隐藏的宠物详细资料，不提供通过 query / hash 切换丢失状态的开关。

页面由 Petvewi_end 的 NFC 渲染器生成；丢失演示删除了扫码请求。App 按钮使用现有开发客户端的 `pethealthrn://` 根入口，不虚构 NFC 绑定。

## 正式接入的边界

此仓库没有数据库，也不判断真实 `lossStatus`；单独的 `lost.html` 只用于查看设计，不能当作安全的状态控制。不要把真实电话、凭据或私人资料提交到公共 Git 仓库（历史记录也会保留）。

正式一宠一链需要公网 HTTPS 后端提供匿名的最小化 NFC API，服务端用 16 字符不可预测令牌查询，只有 `LOST` 才返回获准公开资料；`SAFE` 只返回头像。Pages 再以 no-store 请求该 API，失败时关闭资料展示。当前本地隐私实现尚未部署，不声称本静态站已接通线上数据库。

GitHub Pages 从 main 分支仓库根目录发布。静态资源仅同源，不依赖外部字体、CDN 或本机地址；链接是否能从某个网络访问取决于该网络是否允许访问 GitHub Pages。
