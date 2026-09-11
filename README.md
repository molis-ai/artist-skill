# artist-skill

艺术风格 Skill 与研究记录。四个 Skill 独立使用，集中维护在此仓库；创作试样仅保存在本地。

| Skill | 用途 | 作品与记录 |
| --- | --- | --- |
| [wes-anderson-poster](skills/wes-anderson-poster/SKILL.md) | 韦斯·安德森风格海报与场景：电影布景写实、布局比例、道具和建筑叙事、电影色板、标题设计 | 本地 `outputs/` |
| [dali-surrealism](skills/dali-surrealism/SKILL.md) | 达利风格超现实绘画：变形、双重图像、体积配色与可见母题 | 本地 `outputs/` |
| [monet-impressionism](skills/monet-impressionism/SKILL.md) | 莫奈风格绘画：光照色板、交织笔触、边缘与时期选择 | 本地 `outputs/` |
| [art-style-skill-builder](skills/art-style-skill-builder/SKILL.md) | 从原作观察、色彩与色板研究和图像反馈中创建或修订独立艺术风格 Skill | [达利试行研究](docs/research/art-style-skill-builder.md) |

```text
skills/
  <skill-name>/
    SKILL.md
    agents/openai.yaml
    references/         创作时需要的文字参考（按需）
    licenses/           随包数据的来源与许可（按需）
    outputs/<topic>/     本地图片、各版本、提示与已有评审（不推送）
docs/research/          艺术风格研究与验证记录
dist/                  本地独立包、合集及旧包归档（不推送）
specs/                 本次整合需求与验收
```

使用时调用原来的 Skill 名称，例如 `$wes-anderson-poster`、`$dali-surrealism`、`$monet-impressionism` 或 `$art-style-skill-builder`。本机 `.codex/skills` 与 `.agents/skills` 的对应入口均链接到 `skills/` 中的源码；编辑这里即可，无需同步多份安装副本。其他电脑可将所需 Skill 安装到自己的发现目录，或使用 `dist/` 中的独立包。

作品按“Skill → 题材 → 版本”归档，保留原文件名和已有评价。`poster.png` / `poster.jpg` 是原目录沿用的主文件名，不自动代表用户验收通过；试图、失败版本和修改过程见各题材记录。实际提示与只有简要说明的旧归档记录有明确区分。

字体与色板交互示意收在韦斯输出的 `typography-and-palettes/`，迷失案例中另保留当时的具体配色清单。莫奈研究见 [研究与验证](docs/research/monet-impressionism.md)。

韦斯的 [场景组织方法](skills/wes-anderson-poster/references/scene-composition.md) 在道具系统、建筑主导或多人叙事时按需读取，涵盖阵列、分区、人物行动、剖面及留空；海报默认和字体规范继续保留。

`dist/` 的当前独立包与 `artist-skill.zip` 包含各 Skill 的 `SKILL.md`、`agents/openai.yaml`、必要的 `references/` 文字参考及随附数据的 `licenses/` 通知，不含作品、用户参考图或研究资料。韦斯包内的 [22 组电影色板](skills/wes-anderson-poster/references/wes-palettes.md) 保留上游准确 HEX，[来源与 MIT 许可](skills/wes-anderson-poster/licenses/wesanderson-MIT.txt) 单独随包保存；莫奈与达利的工作色板方法写在各自正文中，属于按光照与造型选择的创作建议。旧的两 Skill 合集位于本地 `dist/archive/`。所有层级的 `output/`、`outputs/` 及生成包 `dist/` 均不纳入 Git；仓库保留 Skill 源码、文字参考、许可和研究及验收文档。
