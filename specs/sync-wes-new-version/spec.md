# 将精简后的韦斯 Skill 合入 artist-skill

## 背景与目标

独立仓库 `wes-anderson-poster` 在 2026-09-11 完成 `wes-style-priority` 重写后拆出；合集仓 `artist-skill/skills/wes-anderson-poster` 仍是拆仓前的 246 行旧稿。用户要求用新版替换旧版，使合集内韦斯运行规则与独立仓一致。

## 当前行为与问题证据

- 独立仓 `SKILL.md` 100 行：场面、机位、实体配色优先。
- 合集仓 `SKILL.md` 246 行：电影布景写实、长英文模板仍在前。
- `agents/openai.yaml` 短描述、`references/scene-composition.md`、色板选用建议同步漂移；22 组 HEX 与许可仍相同。
- 重叠的历史 specs（layout / palettes / scene-grammar / set-realism）两边已一致；合集缺少 `wes-style-priority`。

## 范围与非目标

范围内：

- 用独立仓逐字节覆盖合集的 `SKILL.md`、`agents/openai.yaml`、`references/scene-composition.md`、`references/wes-palettes.md`。
- 复制 `specs/wes-style-priority/` 作为该重写的需求与验收记录。
- 更新根 README 中韦斯一行描述，并标明与独立仓对齐。

非目标：

- 不改达利、莫奈、元 Skill、许可文件、22 组离散 HEX。
- 不重新出图、不宣称新的审美验收。
- 不提交、不推送；本地无 `dist/`，不新建发行包。
- 不改写既有历史 specs 的原文。

## 方案

独立仓是新版唯一来源。合集仓只接收已验收稿，不在合集侧再改规则。许可文件已相同，跳过。

## 文件边界

- 覆盖：`skills/wes-anderson-poster/{SKILL.md,agents/openai.yaml,references/scene-composition.md,references/wes-palettes.md}`
- 新增：`specs/wes-style-priority/{spec.md,validation.md}`、本需求与验收
- 修改：根 `README.md` 韦斯说明
- 禁止：其他 Skill、`licenses/`、历史 wes specs 正文

## 验收标准

1. 上述四个运行文件与独立仓对应文件逐字节相同。
2. 22 组 HEX 与许可相对合集旧稿不变（许可本就相同）。
3. `quick_validate.py skills/wes-anderson-poster` 通过。
4. 其他三个 Skill 无 diff。

## 验证命令

```bash
diff -q skills/wes-anderson-poster/SKILL.md /Users/didi/code/wes-anderson-poster/SKILL.md
python3 /Users/didi/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/wes-anderson-poster
git -C /Users/didi/code/artist-skill diff --stat
```

## 假设

本机当前没有指向该 Skill 的发现入口，也没有本地 `dist/`。完成等级为合集源码与独立仓运行文件对齐；不覆盖发现目录安装或发行包。
