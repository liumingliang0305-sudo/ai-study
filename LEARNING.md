# My AI Engineering Path
<!-- Managed by the ai-engineering-from-scratch learning skills.
     Repo: https://github.com/rohitg00/ai-engineering-from-scratch -->

## Mission
想转行 FDE。目前在做 MCP 和 AI 应用开发，但代码基本由 AI 编写，希望真正理解代码背后的底层原理；最终想构建的项目暂时还不确定。

## Placement
- Date: 2026-08-27
- Score: 4/10 (Math & Statistics 1/2; Classical ML 1/2; Deep Learning 0/2; NLP & Transformers 1/2; Applied AI 1/2)
- Entry point: Phase 3: Deep Learning Core
- Pace: 尽快推进

## Path
| Phase | Name | Status | Est. hours |
|-------|------|--------|------------|
| 0 | Setup & Tooling | Skip | -- |
| 1 | Math Foundations | Review | 23 |
| 2 | ML Fundamentals | Review | 21 |
| 3 | Deep Learning Core | Do | 15 |
| 4 | Computer Vision | Do | 27 |
| 5 | NLP — Foundations to Advanced | Do | 30 |
| 6 | Speech & Audio | Do | 18 |
| 7 | Transformers Deep Dive | Do | 14 |
| 8 | Generative AI | Do | 14 |
| 9 | Reinforcement Learning | Do | 13 |
| 10 | LLMs from Scratch | Do | 26 |
| 11 | LLM Engineering | Do | 17 |
| 12 | Multimodal AI | Do | 65 |
| 13 | Tools & Protocols | Do | 43 |
| 14 | Agent Engineering | Do | 42 |
| 15 | Autonomous Systems | Do | 20 |
| 16 | Multi-Agent & Swarms | Do | 28 |
| 17 | Infrastructure & Production | Do | 32 |
| 18 | Ethics, Safety & Alignment | Do | 31 |
| 19 | Capstone Projects | Do | 620 |

## Progress log
| Date | Lesson | Quiz | Note |
|------|--------|------|------|
| 2026-08-28 | `01-math-foundations/01-linear-algebra-intuition` | 3/3 | 理解了 Gram-Schmidt 通过减去投影去除重叠方向；需要用纯文本展示公式，并继续巩固 LoRA 的低秩矩阵尺寸与乘法。 |

## Current checkpoint
- Date: 2026-08-28
- Next lesson: `01-math-foundations/02-vectors-matrices-operations`
- Resume at: Start the lesson.
- Evidence: Completed Linear Algebra Intuition with quiz score `3/3`; explained Gram-Schmidt as subtracting overlapping projections, traced the scratch implementation, and explained how LoRA forms a full-size update from two trainable low-rank matrices.

## Lesson notes

### 线性代数直觉

- **向量（Vector）**：表示点、方向或一组特征的数字列表。例如 `[3,2]`。
- **向量长度（Magnitude）**：向量的长度。公式：`||a|| = sqrt(a1^2 + a2^2 + ... + an^2)`。
- **矩阵（Matrix）**：把输入向量转换成输出向量的变换。矩阵乘向量时，矩阵的每一行与输入向量做一次点积，产生一个输出值。
- **点积（Dot product）**：衡量两个向量的方向对齐程度，同时也保留长度的影响。公式：`a·b = a1*b1 + a2*b2 + ... + an*bn`。
  - 大于 0：方向总体一致。
  - 等于 0：互相垂直。
  - 小于 0：方向总体相反。
- **余弦相似度（Cosine similarity）**：比较方向，并消除向量整体长度的影响。公式：`cos(a,b) = (a·b) / (||a|| * ||b||)`。
  - 例：`cos([1,1],[2,2])` 和 `cos([1,1],[20,20])` 都等于 `1`，因为它们方向相同。
- **线性组合（Linear combination）**：若干缩放后向量的和，例如 `c1*v1 + c2*v2`。
- **线性独立（Linear independence）**：一组向量中，没有任何一个能由其他向量线性组合得到。独立向量会增加已有向量无法覆盖的维度。
  - 例：`[2,1,0] = 2*[1,0,0] + [0,1,0]`，所以它不是相对于前两个向量的独立方向。
- **张成空间（Span）**：一组向量通过所有可能的线性组合能够得到的全部向量。
  - 例：`[1,1]` 和 `[2,2]` 只能张成直线 `x=y`，因为任意组合都是 `[t,t]`。
- **基（Basis）**：能够张成目标空间，并且线性独立、没有冗余的最小向量组。
  - 二维空间的一组基包含 2 个独立向量；三维空间的一组基包含 3 个。
  - 同一向量在不同基下可以有不同坐标。向量 `[4,2]` 在基 `[1,1]、[1,-1]` 下的坐标是 `[3,1]`。
- **秩（Rank）**：独立信息方向的数量，也等于矩阵中线性独立行或列的数量。10 个特征列的秩为 7，表示只有 7 个独立方向，另有 3 个冗余自由度。
- **投影（Projection）**：向量 `a` 沿向量 `b` 方向的分量或“影子”。
  - 公式：`proj_b(a) = ((a·b) / (b·b)) * b`。
  - 推导条件：投影可写成 `p=t*b`，剩余部分满足 `(a-p)·b=0`。
  - 例：把 `[3,4]` 投影到 `[1,0]`，结果是 `[3,0]`。
- **归一化（Normalization）**：把非零向量缩放到长度为 1。公式：`normalize(a) = a / ||a||`。
- **Gram-Schmidt 正交化**：把一组线性独立向量转换成标准正交基；依次减去当前向量在已有基向量上的投影，再将剩余部分归一化。

## Review queue
