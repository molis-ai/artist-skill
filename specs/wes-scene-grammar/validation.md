# 场景方法更新验收

日期：2026-09-11。本轮仅依据用户提供的八段参考 prompt 分析与改写，没有附带成图，不将文本质量视为图像质量的证据。

## 参考输入如何进入 Skill

| 输入 | 可迁移的方法 | 写入后的边界 |
|---|---|---|
| 1 行李寄存室 | 格柜构成容器，道具大小、轮廓、色相与图案在重复结构里变化；门童稳定轴线 | 道具系统可以是视觉主体，不要求同形同色，也不把所有主题改成行李墙 |
| 2 餐厅服务 | 核心行动稳定中心，周围人物各有动作与目光，平衡位置同时保留纵深 | 区分机位朝向与人物目光，不强迫行动场景合影；餐具与手、桌的关系要成立 |
| 3 六房间剖面 | 房间在同一建筑外壳内并行呈现，居民互不知晓，各有主色和活动 | 保留剖面边界、楼板与外部线索；行列数服从用户，不设通用六格模板 |
| 4 两个相邻房间 | 配色、动作和空间分隔表现情绪距离；门洞连接整体并引入局部远景 | 外部平衡不意味着两侧家具与人物镜像；局部纵深不破坏整体正面编排 |
| 5 五连拱座 | 相同结构中的主色序列，共同分隔物连接；空位帮助结构和色区显现 | 场景颜色通过实体呈现，不添加字面色卡；不为满员而补人物 |
| 6 多层大堂 | 楼层、楼梯和平台组成连通结构，小人物的行动形成节奏 | 建筑主导、人物相对小但动作可读；不按背景默认把所有楼层柔焦 |
| 7 无人泳池 | 安静与对称形成稳定秩序，单个郑重而异样的物件成为焦点 | 保留无人和反射要求；异常可有视觉作用而没有剧情解释，不规定必有红伞 |
| 8 大面分区大厅 | 建筑大面承载颜色，小人物与朝向构成情绪重心 | 人物不必居中放大或看镜头；全局统一允许分区各有颜色身份 |

## 人工提示推演

以下是根据新版规则编排的片段，用于检查选择是否相互冲突；未提交给图像工具。

### 原有的竖版人物海报

请求：一位园丁的韦斯海报，主题“After the Rain”，保留人物身份。

选择：沿用 2:3、英文主副标题、人物直接对视和自然比例；庭院陪衬可柔焦。衣物与庭院构成主辅色即可，不为使用新方法增加分房、楼层或道具墙。

> Create one 2:3 cinema poster with the gardener as the visual lead, looking directly into the camera with a calm expression. Keep the figure naturally proportioned and preserve the source identity. Arrange the garden backdrop around a clear frontal axis and soften incidental foliage. Set “After the Rain” as a rounded script wordmark on a gentle arch, with “A quiet season begins.” as a smaller, quiet subtitle; fit the title group into the open space without shortening the figure.

结论：肖像对视、字体与比例默认保留；复杂场景参考不反向支配普通海报。

### 建筑剖面与并行生活

请求：4:3 三层两列公寓剖面，六个居民分别进行用户指定活动，无字。

选择：外壳、楼板和统一视点组织全图；各房间主色和活动不同，人物相对小。动作目标决定目光；所有需要讲故事的房间都保持可读，不预留标题。

> Create one 4:3 frontal architectural cutaway of a single three-storey apartment building, with two rooms per floor. Keep the exposed facade edges, floor slabs and a strip of street visible. Give the six rooms their specified dominant colors and place one resident in each, respectively reading, writing, bathing with a book, sleeping, ironing and listening to records. Each person attends to the activity within their own room, unaware of the others. Keep the residents small relative to doors and furniture, while their actions and contact with objects remain readable across the frame. Render no lettering or title area.

结论：建筑是主角，人数、活动和网格来自本次输入；人物目光、清晰度与无字要求不受旧默认覆盖。

### 无人泳池与局部异常

请求：正面空泳池，中央一把收起的红伞，无人、无字。

选择：泳池、中央拱门与两侧建筑形成秩序；红伞只是有位置与反射的单个焦点。无人时删除全部人物段与表情要求，不添加门童解释伞的来历。

> Photograph an empty indoor swimming bath from a fixed, perfectly frontal viewpoint. Let the turquoise pool and cream-and-mint architecture form the main geometry. Beneath the central arch, place one closed red parasol upright at the far pool edge, with its reflection located consistently in the still water. Leave the room unoccupied and silent, using soft diffused daylight, gentle grain and subdued contrast. No people or lettering.

结论：无人、留空和局部异常成立；没有把主题改成肖像海报或添加额外叙事道具。

## 文件与验证

- **通过**：新版 Skill 已运行 `quick_validate.py`，返回 `Skill is valid!`。
- **通过**：人工审阅主文 scoped diff 与新参考；实际提示及结果检查已同步改为按主角、动作与空间职责选择。字体正文、人物/物件比例规则及色板数据保持。
- **通过**：Codex、Agents、Grok 的既有韦斯入口均可读到新版主文与两份相对参考。
- **通过**：韦斯独立包含 5 个运行/分发文件，合集含 11 个；全部成员和内容逐项与当前源码比对一致，作品与工作记录未进入包。其他三个 Skill 的运行内容与旧合集完全一致。
- **通过**：当前色板正文在本轮开始前已移除来源与许可说明，保留现有正文不改。22 组名称与色值同旧包一致；原有 MIT 通知完整转存到单独的 `licenses/wesanderson-MIT.txt`，来源链接随附，README 已说明位置。
- **未运行**：真实图像生成和视觉验收。这一版只证明规则已更新且内部选择一致，不宣称八组 prompt 的出图效果通过。
