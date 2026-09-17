# wes-anderson-poster

韦斯·安德森风格海报与场景 Skill：端正而有戏的机位、复古美术、成片的布景颜色与统一的胶片色调，以及平静表面下的幽默、等待或疏离。

本仓库从 [artist-skill](https://github.com/molis-ai/artist-skill) 的合集里独立出来，只保留韦斯·安德森这一支，便于单独维护与分发。仓库根目录就是 Skill 目录：`SKILL.md` 是运行入口，其余为其文字参考、随包许可、本地作品与设计记录。

```text
SKILL.md                运行入口：成品与输入、场面设计、实体配色、电影再现、比例边界、艺术标题、提示与检查
agents/openai.yaml      入口短描述与默认提示
references/             按需读取的文字参考
  wes-palettes.md         22 组电影色板（准确 HEX）、选色优先级与画面分配建议
  scene-composition.md    建筑、道具阵列、多人行动与剖面场景的组织方法
licenses/               随包色板数据的来源与 MIT 许可
outputs/                本地作品与各次尝试（不推送）
specs/                  历次需求与验收记录
dist/                   本地独立包（不推送）
```

使用时调用 `$wes-anderson-poster`。默认交付 **2:3 竖版英文海报**（英文主标题＋副标题）与实际提示词；指定剧照或电影场景时默认无字，画幅按需选择。用户指定的内容、媒介、语言、画幅和动作优先。

`references/` 里的两份文字参考按需读取：需要默认配色或命名色板时读色板参考，建筑、道具阵列、多人行动或剖面成为主角时读场景组织方法；普通单主体场景无需加载。

作品按“题材 → 版本”归档在本地 `outputs/`，保留原文件名和已有评价；版本的评价以当时评审为准，归档不表示全部通过。`poster.png` / `poster.jpg` 是沿用至今的主文件名，不自动代表用户验收通过。`docs/`、`outputs/` 与生成包 `dist/` 均不纳入 Git，仓库只保留 Skill 源码、文字参考、许可与需求验收记录。

色板数据来自社区整理的 [karthik/wesanderson](https://github.com/karthik/wesanderson)（MIT，© 2022 Karthik Ram），来源与许可说明见 [licenses/wesanderson-MIT.txt](licenses/wesanderson-MIT.txt)，该许可只覆盖随包色板数据，不许可其余 Skill 内容。色板是社区参考，不是导演官方调色规范；选色优先级、颜色角色与面积分配属于本项目的海报设计建议。

英文艺术标题为本项目的海报适配，不概括导演全部作品；参考依据以《月升王国》《小行星城》等实拍图像与摄影师访谈校准，具体观察与验收记录见 `specs/`。
