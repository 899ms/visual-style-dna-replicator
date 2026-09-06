# Prompt Compiler

结构化 JSON 完成后，按以下顺序压缩成自然语言生图指令。

```text
Use case: <generation or edit mode>
Asset type: <poster, ad, product image, illustration, etc.>
Input images: <Image 1 role; Image 2 role; ...>
Primary request: <what must change>
Scene/backdrop: <environment and negative space>
Subject: <identity, geometry, scale, angle, pose>
Style/medium: <rendering and visual category>
Composition/framing: <grid, placement, crop and focal path>
Lighting/mood: <type, direction, contrast and emotion>
Color palette: <locked colors and area relationships>
Materials/textures: <surfaces and imperfection level>
Typography: <hierarchy, position and exact copy>
Constraints: <must preserve and must change>
Avoid: <specific failure modes>
```

## 编译规则

- 编辑任务第一句写清“只修改什么”，最后再次列出锁定项。
- 多参考图逐张标注职责，不写笼统的“参考所有图片”。
- 精确文字用引号逐条列出，并要求不得改写、重复或增加字符。
- “保持风格”要展开成色彩、构图、材质、字体、光影和装饰语法，不只写风格名称。
- “长大”要写成自然骨架重建，附带头身、胯位和腿长边界；不使用单独的“长腿、超模比例”。
- 负面提示只保留与当前失败风险直接相关的项目。

## 单次修改示例

用户要求把幼年鹿 IP 变为成年角色时：

```text
Use case: identity-preserve
Primary request: Rebuild the childlike deer IP as the same character at natural adulthood. Change age, skeleton, posture and adult clothing fit only.
Subject: preserve the exact face, eyes, ears, antlers, fur colors and signature accessories; use a coordinated 6.5–7-head adult body; pelvis near the vertical midpoint; crotch-to-sole length 47–50% of total height; complete torso, natural knees, ankles, hands and shoes.
Pose: three-quarter 35–45° stance created by shoulder, rib-cage and pelvis rotation with stable weight distribution.
Constraints: keep identity, palette, brand spelling and poster layout unchanged.
Avoid: stretched legs, shortened torso, 8–9-head fashion anatomy, high hips, oversized shoes, identity drift, extra fingers, cropped feet.
```

## 生成后的定向迭代

一次只修一个问题：

- 身份漂移：加强 `identity_anchors`，其余不变。
- 腿过长：要求重建骨盆、躯干和膝盖位置，不只做纵向缩放。
- 版式漂移：将上次结果设为 `edit_target`，锁定画布和文字。
- 材质廉价：只修表面粗糙度、反射和光影，不改构图。
- 文字错误：只做文字替换或后期排版，不重绘主体。
