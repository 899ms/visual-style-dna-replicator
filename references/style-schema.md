# Style DNA JSON Schema

需要建立新风格、归类参考图或复用系列视觉时，使用此结构。字段值应是可观察描述、画布比例或合理区间，避免伪精确。

```json
{
  "profile": {
    "name": "",
    "category": "",
    "confidence": 0.0,
    "reference_count": 0,
    "shared_dna": [],
    "variable_traits": []
  },
  "canvas": {
    "aspect_ratio": "",
    "orientation": "",
    "safe_margin_percent": [0, 0],
    "output_use": ""
  },
  "subject_system": {
    "type": "",
    "identity_anchors": [],
    "body_or_object_geometry": {},
    "canvas_occupancy_percent": [0, 0],
    "position": "",
    "view_angle_degrees": [0, 0],
    "pose_or_orientation": "",
    "supporting_elements_percent": [0, 0]
  },
  "composition_system": {
    "archetype": "centered | left-right | top-middle-bottom | diagonal | asymmetric-editorial | other",
    "grid": "",
    "focal_path": "",
    "depth_layers": [],
    "white_space_percent": [0, 0],
    "balance": "",
    "crop_rules": []
  },
  "color_system": {
    "palette": [{"role": "", "hex_estimate": "", "share_percent": [0, 0]}],
    "saturation": "low | medium | high",
    "brightness": "low | medium | high",
    "contrast": "low | medium | high",
    "temperature": "cool | neutral | warm",
    "accent_rule": ""
  },
  "lighting_system": {
    "type": "soft studio | hard studio | indoor ambient | outdoor daylight | backlight | silhouette | volumetric | other",
    "direction": "",
    "key_fill_ratio": "",
    "shadow": "",
    "atmosphere": ""
  },
  "typography_system": {
    "headline": {"style": "", "case": "", "weight": "", "scale_percent": [0, 0], "position": ""},
    "secondary": {"style": "", "scale_relation": "", "position": ""},
    "reading_direction": "",
    "alignment": "",
    "density": "",
    "exact_copy": []
  },
  "material_system": {
    "medium": "photo | 3d | vector-like | pencil | ink | collage | mixed",
    "surface": [],
    "grain": "",
    "edge_quality": "",
    "retouching": "",
    "imperfection": ""
  },
  "decorative_system": {
    "elements": [],
    "frequency": "",
    "placement_rule": "",
    "interaction_rule": ""
  },
  "brand_lock": {
    "locked_assets": [],
    "locked_spelling": [],
    "locked_colors": [],
    "allowed_transformations": [],
    "forbidden_transformations": []
  },
  "generation_controls": {
    "must_preserve": [],
    "must_change": [],
    "negative_constraints": [],
    "verification_checks": []
  },
  "final_prompt": ""
}
```

## 系列归类

新图片进入已有体系时，分别计算以下五组相似性，不用单一“像/不像”判断：

- 构图与留白 25%
- 色彩与明暗 20%
- 材质与渲染 20%
- 字体与信息层级 20%
- 主体呈现与装饰语法 15%

`80–100` 可归为同一风格；`60–79` 归为同一母风格的变体；低于 `60` 建立新风格。若用户强调某项，允许调整权重并说明。
