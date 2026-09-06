# Visual Style DNA Replicator

A portable Codex/Agent Skill for reverse-engineering reference images into reusable visual systems, then generating consistent new images while keeping style, identity, layout, text, and proportions under control.

## 能做什么

- 分析单张或多张参考图的主体比例、留白、色彩、构图、光影、文字和材质
- 把视觉风格转换成稳定的 JSON 变量体系
- 判断新图片属于同一风格、母风格变体还是新风格
- 在锁定风格的情况下替换主体、产品、角色、文案或配色
- 根据风格系统直接生成或编辑图片
- 防止“长大、修长”等要求被错误处理为四肢任意拉伸

## 安装到 Codex

仓库发布后，可让 Codex 安装：

```text
请从 https://github.com/hanfeer/visual-style-dna-replicator 安装这个 Skill。
```

也可以手动安装：

```bash
git clone https://github.com/hanfeer/visual-style-dna-replicator.git
mkdir -p ~/.codex/skills
cp -R visual-style-dna-replicator ~/.codex/skills/
```

重新启动 Codex 或新建任务后，可以这样调用：

```text
使用 $visual-style-dna-replicator 分析这组参考图，把它转换成可复刻的风格系统。
```

## 安装到其他 Agent

支持通用 Agent Skills 目录的运行环境，可以直接安装到：

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/hanfeer/visual-style-dna-replicator.git ~/.agents/skills/visual-style-dna-replicator
```

若目标 Agent 使用自己的 Skill 目录，把整个仓库复制到它的 skills 目录即可；必须保留 `SKILL.md`、`agents/` 和 `references/` 的相对结构。

## 目录

```text
visual-style-dna-replicator/
├── SKILL.md
├── agents/openai.yaml
└── references/
    ├── analysis-rubric.md
    ├── prompt-compiler.md
    └── style-schema.md
```

`SKILL.md` 是入口；Agent 只在需要时读取相应参考文件，以减少上下文占用。
