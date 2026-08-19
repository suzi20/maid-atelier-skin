# 个人修改说明 · Personal Modifications

本仓库为 [Small-tailqwq/dsh-deep-whale](https://github.com/Small-tailqwq/dsh-deep-whale)
（鲸鱼娘皮肤系列）中 **maid-atelier（深海女仆工坊）** 皮肤的**个人自用修改版**。

> 仅作个人使用与备份。若需分享或二次分发，请遵守 CC BY-NC-SA 4.0：
> 保留完整署名链、非商业性使用、以相同方式共享。完整署名链见各皮肤 `NOTICE` 与本文件末尾。

## 修改内容（相对上游 Small-tailqwq/dsh-deep-whale）

### 1. 布局微调
- 侧栏底部（`[data-maid-sidebar-footer]`）由固定高度改为**自适应高度**
  （`flex: 0 0 auto` + `min-height`）：GUI 新版 footer 同时包含 Cordis 插件
  徽章行与设置按钮，上游的固定高度会裁掉设置按钮。
- 输入框（composer）去掉了顶部带蝴蝶结的九宫格装饰边框，改为**简洁的
  1px 金色细描边**，不再向外扩张遮挡内容。
- 双女仆角色整体略微缩小（高度约 88vh / 84vh），对话状态进一步退让。

### 2. 明暗与对比度
- 背景宫殿增加一层**浅海军蓝纱幕**（`body::before`），亮/暗模式各自压暗，
  使前景更稳、更耐看。
- 角色、吉祥物、花边等装饰元素**不透明度整体降低一档**（角色约 78%、
  吉祥物 70%、顶/底花边 85%），并降低暗色模式下的饱和度与亮度。
- 金色强调（边框、选中态、徽章光晕）**下调到中间档**，不再刺眼。

### 3. 文字突出（重点改动）
- **Agent 输出正文**：亮色模式下强制近黑 `#0c1428`，气泡背景提高至
  97% 不透明，段落/标题/列表/引用等全部覆盖，不再受角色透出干扰。
- **底部统计行**（StatsLine：`4 轮 · 147 步 | LLM ... | 缓存命中 ...`）：
  亮色纯黑 `#000` + 加粗 600，分隔符同步加深。
- **消息尾部时间戳**（`15:27 · 用时 2分51秒 · 首 token 3.6秒`）：亮色近黑。
- **Think 行**（推理折叠行）：标题加粗 600，摘要/正文加粗 500，亮暗模式
  都提高了对比。
- **输入框**：草稿文字、placeholder、命令 hint 全部提亮/加深并加粗，
  输入框卡片背景不透明度提高到 93% / 95%。
- 全局弱化色 token 加深：`label-secondary` `#4d5d7f → #33415f`、
  `label-tertiary` `#6f7c99 → #273352`、`label-caption` `#8a94aa → #4d5a78`
  （暗色模式对应提亮），从根源上提升所有次要文字的清晰度。

## 实现方式

- 所有改动均在皮肤包内完成，不修改任何产品代码：
  - `maid-atelier/src/client/maid-atelier.module.css` —— 全部视觉调整
  - `maid-atelier/src/client/index.ts` —— 新增 `decorateStatsLine()`（给统计
    行打 data 钩子，配合 CSS 提升对比；现已用纯 CSS 结构选择器兜底）
- 修改后通过皮肤包自带的 `tsdown` 重新构建 `maid-atelier/lib/client.js`，
  安装与热更新方式与上游一致（`dsh plugin --profile web add <path>`）。

## 版权与署名链

| 版权所有人 | 版权所有内容 | 个人主页 |
|---|---|---|
| 上善 | 鲸鱼娘角色形象原作（一创） | [Pixiv](https://www.pixiv.net/users/62155430) · [Bilibili（上善无形）](https://b23.tv/8h5L4xz) |
| ZipZipPipe | 加入 DeepSeek 元素的女仆鲸鱼娘二次设计（二创） | [Pixiv](https://www.pixiv.net/users/18604994) · [Bilibili（ZipZipPipe）](https://b23.tv/Pnw6nG8) |
| Small-tailqwq | 本皮肤（三创）与素材再设计 | [GitHub](https://github.com/Small-tailqwq/dsh-deep-whale) |
| 皮肤工程脚手架 | dsh-web-ui（目录模板、构建预设） | [zhu1090093659/dsh-web-ui](https://github.com/zhu1090093659/dsh-web-ui) |

本修改版整体以 **CC BY-NC-SA 4.0** 发布（署名-非商业性使用-相同方式共享），
**禁止商业性使用**。完整许可文本见 `maid-atelier/LICENSE`。
