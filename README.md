# Childhood AI Avatar Skill

一个面向 Codex 的童年头像生图与风格复刻 skill。它根据用户提供的身份照片生成单张、四张或九张一致头像，并可附加 2×2 / 3×3 合集。

## 这版解决了什么

- 明确区分**身份参考图**与**风格参考图**，禁止示例图“带偏脸”
- 九张图逐张生成、逐张质检，降低九宫格一次生成造成的身份漂移
- 支持“同风格九表情”和“同构图九风格”两种模式
- 内置九种风格配方：棚拍、毛绒、黏土、动漫、水彩、复古儿童照、贴纸、盲盒、剪纸
- 用 5 分质量门槛检查身份、套图一致性、变体清晰度与技术瑕疵
- 九宫格只排版已通过质检的单图，不重新生成面孔
- 对儿童形象强制使用适龄服装、姿势和道具

## 仓库结构

```text
skills/childhood-ai-avatar/
├── SKILL.md
├── agents/openai.yaml
└── references/
    ├── set-recipes.md
    └── style-recipes.md
```

## 安装

将 `skills/childhood-ai-avatar` 复制到 Codex skills 目录：

```powershell
Copy-Item -Recurse -Force .\skills\childhood-ai-avatar "$env:USERPROFILE\.codex\skills\childhood-ai-avatar"
```

重新打开相关 Codex 任务后即可使用。

## 调用示例

```text
使用 $childhood-ai-avatar，根据我上传的童年照片生成九张白底半写实头像，
分别使用不同表情，再额外做一张 3×3 九宫格合集。
```

```text
使用 $childhood-ai-avatar，把我的童年照片做成九种风格对比；
示例图只参考风格，不要参考示例人物的脸。
```

## 许可

[MIT License](LICENSE)
