# 短片制作 Skills

本目录把三款 AI 短片创作 Skill 放在一起，并用中文标注用途。仓库目前是公开仓库，已提交的文件对所有人可见。

## 目录

| 文件夹 | Skill 调用名 | 用途 | 内容情况 |
|---|---|---|---|
| `01_导演总控_Seedance_Director` | `$seedance-director` | 规划剧情、镜头、提示词和生成验收。 | 仅中文说明与上游链接；完整包包含校准资料和项目测试样例，未复制到公开仓库。详情见该目录 README。 |
| `02_电影视觉_Cinema_DNA` | `$cinema-dna-21x9x3` | 设计电影静帧、三联画或九镜故事板，确定构图、光线和逐镜动作。 | Skill 说明、参考资料和拼版脚本。 |
| `03_即梦提示词_Seedance_2_5` | `$seedance-2-5` | 编写、改写和优化即梦 Seedance 2.5 视频提示词。 | Skill 说明及官方指南、提示词范例。 |

## 配合方式

1. 用 **Seedance Director** 规划剧情、镜头和生成验收要求。
2. 用 **Cinema DNA** 细化关键镜头的画面、构图和光线。
3. 用 **Seedance 2.5** 将镜头要求整理成即梦可用提示词，或快速试拍单个镜头。
4. 将试拍结果交回 **Seedance Director** 检查并安排修改。

## 上游项目

- [Seedance Director](https://github.com/gifted-professor/seedance-director)
- [Cinema DNA 21x9x3](https://github.com/dacnay816y62-hub/cinema-dna-21x9x3)
- [Seedance 2.5 Prompt Skill](https://github.com/xiaoliangliang/seedance-2.5-prompt-skill)

各 Skill 的源文件与许可信息以各自上游项目为准。