# 学院派视觉笔记插画 Skill

> 把任何一段文字，变成一张「实验室研究记录」质感的手绘视觉笔记插画，并产出豆包 / 即梦 / Midjourney 可用的精准提示词。
>
> Turn any paragraph into an academic hand-drawn "visual notes" illustration — with ready-to-use image-generation prompts.

[English README →](./README_EN.md) · [示例 Example →](./examples/perovskite-visual-note-prompt.md)

![示例：钙钛矿「可调门槛」视觉笔记（9:16 竖版）](./assets/perovskite-example.png)

---

## 一、它解决什么问题

给 AI 一段文字说「画张图」，结果往往是一张漂亮的废话：元素堆砌、文字错乱、和原文关系不大。

这个 Skill 把「文字 → 插画」拆成一条**可控制的流水线**：先定画幅，再拆思想框架，再由你从 20 个候选中**亲自选一个核心主体**，最后才生成提示词并出图。主体由你拍板，所以画出来的东西一定是你要的那张。

## 二、五步工作流

| 步骤 | 做什么 | 产出 |
|---|---|---|
| ① 选画幅 | 16:9 / 4:3 / 3:4 / 9:16，四选一 | 构图与像素规格 |
| ② 拆结构 | 中心思想 → 主标题；次级论点 → 分区；提炼概念词 → 中英双语标签 | 思想框架拆解表 |
| ③ 选主体 | 从 50 元素池随机抽 20 个，列出编号供选 | 唯一核心主体 |
| ④ 出提示词 | 按模板填充，输出完整版 + 120 字精简版 | 豆包可用提示词 |
| ⑤ 出图 | 调用图像模型生成，不满意按要素迭代 | 成品插画 |

## 三、画幅规格

| 比例 | 像素 | 适用场景 |
|---|---|---|
| 16:9 横版 | 1920×1080 | 公众号头图、汇报封面、宽屏阅读 |
| 4:3 横版 | 1184×888 | 经典讲义版式、嵌入文档 |
| 3:4 竖版 | 896×1152 | 论文配图、笔记页 |
| 9:16 竖版 | 1080×1920 | 手机长图、社媒海报 |

## 四、视觉规范（这是风格的骨架）

- **画布**：纯白主色 + 极淡 5mm 打印方格纸网格，四周不留深色底图
- **线条**：HB / 2B 铅笔素描干练线条；阴影用排线（hatching / cross-hatching）
- **制图元素**：尺寸线、箭头、坐标轴线、角度弧线、向量、剖面符号、编号标签
- **学科公式**：按主题穿插 3–5 处数学 / 物理 / 化学 / 生物公式（手写体）
- **色彩**：黑白灰为主，关键处低饱和马克笔淡彩，**彩色面积 < 12%**
- **手写批注**：4–6 处潦草可读的中文批注，带下划线与圈注
- **学院派细节**：便签贴、回形针、胶带痕、装订孔、红色批阅笔迹、页边编号
- **隐藏纹样**：中国传统回纹 / 古希腊瓶画 / 阿拉伯几何纹 / 曼荼罗 / 安第斯编织纹 / 波斯细密画，六选一，作极淡底纹
- **文字纪律**：印刷体双语标签，画面内不出现任何与底本无关的词语

## 五、50 元素池（每次随机抽 20 个供选）

棱镜折射塔、齿轮树、神经元珊瑚、悬浮罗盘、裂解原子核、双螺旋阶梯、沙漏引擎、折叠纸城、根系网络、蜂巢穹顶、水晶方尖碑、折纸飞鸟、齿轮心脏、洋葱剖面球、分形蕨叶、杠杆天平、迷宫石板、气泡上升塔、钟摆轨道、多级火箭、熔炉坩埚、种子萌发舱、磁悬浮陀螺、管道蔓延体、拼图立方、阶梯金字塔、光纤花束、蜂群阵列、锁钥机构、透镜眼球、漩涡漏斗、破碎面具、拱桥结构、风车叶片、树轮年盘、折叠地图、血管树、冰晶晶格、火山剖面、齿轮罗盘、孵化蛋体、电路板山脉、滑轮组、涟漪水面、阶梯瀑布、俄罗斯套娃、抛物线弹道、月相盘、日晷指针、螺旋星系盘

## 六、安装

```bash
# WorkBuddy（用户级）
git clone https://github.com/<你的用户名>/visual-notes-illustrator.git \
  ~/.workbuddy/skills/visual-notes-illustrator

# Claude Code（用户级）
git clone https://github.com/<你的用户名>/visual-notes-illustrator.git \
  ~/.claude/skills/visual-notes-illustrator
```

也可以直接下载 `SKILL.md` 放进 skills 目录，Skill 会靠 YAML frontmatter 的 `name` / `description` 自动触发。英文用户请把 `SKILL_EN.md` 改名为 `SKILL.md` 后使用（原始英文版不带 frontmatter，是为避免与中文版重复注册）。

## 七、怎么用

```
用视觉笔记插画 skill，把下面这段做成 9:16 竖版：
<粘贴正文>
```

Skill 会先问画幅，再拆结构，再给你 20 个编号，你回一个数字，它出提示词并出图。

## 八、目录结构

```
visual-notes-illustrator/
├── SKILL.md                 # Skill 本体（中文，带 frontmatter，直接可用）
├── SKILL_EN.md              # Skill 英文参考版（无 frontmatter，需用时改名为 SKILL.md）
├── README.md                # 本文件
├── README_EN.md             # English README
├── LICENSE                   # MIT
├── .gitignore
├── assets/
│   └── perovskite-example.png          # 示例成图
└── examples/
    └── perovskite-visual-note-prompt.md # 示例提示词（完整版 + 精简版）
```

## 九、示例

底本是一段讲钙钛矿带隙可调的科普文字，选了 **12 号「沙漏引擎」**：沙漏 = 能量门槛的筛选机制，腰部可调阀门 = 1.2–3.0 eV 连续可调的带隙，下腔 = 钙钛矿 / 晶硅叠层电池。完整提示词见 [examples](./examples/perovskite-visual-note-prompt.md)。

## 十、License

MIT © AIOpenVC
