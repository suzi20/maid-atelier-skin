# dsh-deep-whale · 鲸鱼娘皮肤系列（个人修改版）

> **本仓库为个人自用修改版，非原仓库。**
> 上游：https://github.com/Small-tailqwq/dsh-deep-whale
> 修改者：su-ziyang（个人使用与备份）

基于 DeepSeek Harness Web GUI 的鲸鱼娘主题皮肤 **maid-atelier（深海女仆工坊）**
的个人修改：在保留全部元素的前提下，调整了部分布局（侧栏底部自适应、
输入框去掉蝴蝶结装饰框）、整体明暗深浅，并显著提升文字对比度与可读性。
详细修改内容见 [MODIFICATIONS.md](MODIFICATIONS.md)。

## 效果预览

| 亮色模式 | 暗色模式 |
|---|---|
| [![maid-atelier 亮色模式](maid-atelier/preview/light.webp)](maid-atelier/preview/light.webp) | [![maid-atelier 暗色模式](maid-atelier/preview/dark.webp)](maid-atelier/preview/dark.webp) |

## 住户

| 皮肤 | 包名 | 说明 | 许可 |
|---|---|---|---|
| [maid-atelier](maid-atelier/) | `@dsh-external/dsh-client-ui-skin-maid-atelier` | 深海女仆工坊：双女仆背景、深海蓝蕾丝界面与 Q 版侧栏（个人修改版：布局微调 + 明暗调整 + 文字突出） | CC BY-NC-SA 4.0 |

## 安装

```sh
git clone <本仓库地址>
cd <harness>
dsh plugin --profile web add ../dsh-deep-whale/maid-atelier
```

加载即生效、卸载即复原；修改版已重新构建 `lib/client.js`，支持皮肤
自带的 HMR 热更新。

## 版权所有人（完整署名链）

| 版权所有人 | 版权所有内容 | 个人主页 |
|---|---|---|
| 上善 | 鲸鱼娘角色形象原作 | [Pixiv](https://www.pixiv.net/users/62155430) · [Bilibili（上善无形）](https://b23.tv/8h5L4xz) |
| ZipZipPipe | 加入 DeepSeek 元素的女仆鲸鱼娘二次设计 | [Pixiv](https://www.pixiv.net/users/18604994) · [Bilibili（ZipZipPipe）](https://b23.tv/Pnw6nG8) |
| Small-tailqwq | 皮肤（三创）与素材再设计 | [GitHub](https://github.com/Small-tailqwq/dsh-deep-whale) |
| zhu1090093659 | 皮肤工程脚手架（dsh-web-ui） | [GitHub](https://github.com/zhu1090093659/dsh-web-ui) |

## 许可

本仓库各皮肤为**衍生创作**，整体以 CC BY-NC-SA 4.0（署名-非商业性使用-
相同方式共享）发布，**禁止商业性使用**。署名链见各皮肤 `NOTICE` 与
[MODIFICATIONS.md](MODIFICATIONS.md)。
