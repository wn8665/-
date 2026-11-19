# 短片制作 Skills

本目录集中存放三款用于 AI 短片创作的 Codex Skills。目录名和下方说明使用中文标注；各 Skill 的源文件保持原样，便于 Codex 识别和使用。

## 目录

| 文件夹 | Skill 调用名 | 中文用途 | 上游项目 |
|---|---|---|---|
| `01_导演总控_Seedance_Director` | `$seedance-director` | 把剧情编成可执行的视频制作计划、分镜提示词与素材清单，并审核生成结果。作为短片项目的导演总控。 | [gifted-professor/seedance-director](https://github.com/gifted-professor/seedance-director) |
| `02_电影视觉_Cinema_DNA` | `$cinema-dna-21x9x3` | 设计电影静帧、三联画或九镜故事板，确定构图、光线、空间关系和逐镜动作。 | [dacnay816y62-hub/cinema-dna-21x9x3](https://github.com/dacnay816y62-hub/cinema-dna-21x9x3) |
| `03_即梦提示词_Seedance_2_5` | `$seedance-2-5` | 编写、改写和优化可用于即梦 Seedance 2.5 的视频提示词。 | [xiaoliangliang/seedance-2.5-prompt-skill](https://github.com/xiaoliangliang/seedance-2.5-prompt-skill) |

## 配合方式

1. 用 **Seedance Director** 规划剧情、镜头和生成验收要求。
2. 用 **Cinema DNA** 细化关键镜头的画面、构图和光线。
3. 用 **Seedance 2.5** 将已确定的镜头要求整理成即梦可用提示词，或快速试拍单个镜头。
4. 将试拍结果交回 **Seedance Director** 检查并安排修改。

建议以 Director 维护当前正式分镜和最终提示词，其他 Skills 的视觉方案与试拍提示词回填到同一份制作计划中。

## 安装到 Codex

这些文件目前作为仓库资料保存。若要让 Codex 在本仓库中自动发现 Skill，可将对应目录放在仓库根目录的 `.agents/skills/` 下；若已安装到个人 Skills 目录，也可通过 `$seedance-director`、`$cinema-dna-21x9x3`、`$seedance-2-5` 调用。

## 来源与许可

各 Skill 的原始文件和许可随对应目录保留。更新时请以表格中的上游仓库为准，并遵守各自许可条款。
