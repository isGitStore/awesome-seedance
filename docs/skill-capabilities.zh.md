# Seedance Skill 功能说明

这个仓库里的 `agents/skills` 不是普通示例文件，而是一组可以装进 Claude Code、Codex 等 agent 的 Seedance 视频提示语工作流。装好以后，你可以直接用自然语言说想要什么视频，agent 会按真实案例沉淀出的结构来写提示语。

## 核心能力

| 功能 | 具体能做什么 |
| --- | --- |
| 提示语生成 | 把一句普通需求扩写成完整 Seedance 提示语，包含主体、镜头、场景、时间轴、动作、声音和负面约束。 |
| 自动选模板 | 按用途选择已经验证过的结构：广告、UGC、口播对话、动作、旅行、宠物、恐怖、奇幻、汽车、时尚、运动、3D 卡通等。 |
| 风格控制 | 调用风格库，在不改主体和剧情要求的前提下，一次生成多种可选画风。 |
| 参考图锁定 | 明确哪些细节必须继承参考图，哪些细节不能串到其他角色、产品或场景里。 |
| 分镜转视频 | 支持先做编号分镜图，再把分镜图连接成 Seedance 视频镜头提示语。 |
| 案例校验 | 用真实案例经验、常见失败点和示例输出检查草稿，减少跑偏。 |
| 专项片型生成 | 针对反转搞笑、奇幻科幻、复古 DV、3D 卡通、宠物、汽车、时尚、恐怖、运动等片型，使用单独 Skill。 |

## 已包含的本仓 Skill

| Skill | 适合什么需求 |
| --- | --- |
| `seedance-prompt-library` | 总控模板库。适合不知道该选哪个片型时使用，覆盖全部分类模板和风格库。 |
| `seedance-meme-comedy` | 反转搞笑短片、梗视频、荒诞但镜头严肃的短剧。 |
| `seedance-epic-fantasy-scifi` | 巨龙、怪兽、机甲、世界观展示、史诗级奇幻或科幻场面。 |
| `seedance-retro-dv-home-video` | 早年 DV、VHS、家庭录像、旧磁带质感、年代感生活片段。 |
| `seedance-3d-cartoon` | 3D 卡通角色、拟人小角色、皮克斯/黏土/玩具质感短片。 |
| `seedance-storyboard-grid-to-video` | 先做九宫格或多格分镜图，再把分镜图转成视频。 |
| `seedance-travel-city-walk` | 城市漫步、旅行 Vlog、黄金时刻、电影感旅拍。 |
| `seedance-pet-animal` | 猫狗、狐狸、动物自拍、动物作为主角的短片。 |
| `seedance-car-vehicle` | 汽车广告、车辆高速运动、镜头围绕车辆切换。 |
| `seedance-fashion-lookbook` | 时尚大片、Lookbook、人物肖像、穿搭短片。 |
| `seedance-horror-suspense` | 恐怖、悬疑、身体变化、门后反转、压迫感镜头。 |
| `seedance-sports-extreme` | 极限运动、跑跳落地、动作链条、运动物理约束。 |

## 怎么安装

安装总控模板库：

```bash
npx seedance-prompt-library install
```

安装单个专项 Skill，例如宠物动物短片：

```bash
npx skills add LearnPrompt/awesome-seedance --skill seedance-pet-animal
```

如果你使用的是这个 fork，也可以把仓库名换成：

```bash
npx skills add isGitStore/awesome-seedance --skill seedance-pet-animal
```

## 怎么使用

安装后不需要背模板，直接说目标即可，例如：

```text
用 Seedance 做一个 10 秒猫咪自拍 vlog，猫咪举着手机在家里走一圈，画面要像真实手机拍摄，不要卡通。
```

agent 会做三件事：

1. 判断这是宠物/动物主角和手机自拍场景。
2. 选择对应 Skill 或模板结构。
3. 输出带镜头、动作、时间轴和负面约束的完整 Seedance 提示语。

## 文件位置

所有 Skill 文件都在：

```text
agents/skills/
```

总控模板库在：

```text
agents/skills/seedance-prompt-library/
```

单片型 Skill 例如：

```text
agents/skills/seedance-pet-animal/
agents/skills/seedance-car-vehicle/
agents/skills/seedance-horror-suspense/
```
