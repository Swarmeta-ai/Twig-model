# Twig v0 alpha

**多语言文本到图像模型，具备强大的指令跟随和长上下文能力**

[English README](README_en.md) | 中文 README

## 模型详情 (Model Details)

🤗链接：[Swarmeta-AI/Twig-v0-alpha](https://huggingface.co/Swarmeta-AI/Twig-v0-alpha)

### 模型描述 (Model Description)

**Twig v0 alpha** 是一个基于 [Efficient-Large-Model/Sana_1600M_1024px_MultiLing](https://huggingface.co/Efficient-Large-Model/Sana_1600M_1024px_MultiLing) 的多语言文本到图像 (Text-to-Image, T2I) 模型。 它的核心设计目标是 **强大的指令跟随能力**，能够更好地理解和执行用户的文本指令。  Twig v0 alpha **直接支持英语和中文的提示词**，无需额外的语言切换或处理。

Twig v0 alpha 的一个关键特性是其 **长上下文能力，支持高达 1200 个 tokens 的输入**。这使得用户能够对生成的图像构成和细节进行更精细的控制，通过更详细的指令来引导图像生成过程。

尽管模型参数量相对较小，仅有 **16 亿参数**，Twig v0 alpha 在 **指令跟随性能方面表现出色，甚至超越了一些参数量更大的闭源模型 (例如 200 亿参数的模型)**。在全面的评估中，它也展现出了 **超越 Flux-dev (120 亿参数) 等模型的性能**。

值得注意的是，Twig v0 alpha 针对效率进行了优化。它可以在 **现代 CPU 上约 10 秒内生成高达 2048x2048 分辨率的大尺寸图像，无需专用 GPU**。 在单个 NVIDIA 4090 GPU 上，生成 1024x1024 图像仅需约 0.4 秒。

Alpha 版本使用了一个 **约 6 万个精心策划的图像-文本对数据集** 进行训练。未来的迭代版本，包括 Beta 版本，将侧重于扩展数据集并探索创新的训练方法。 **Version 1 (v1) 计划引入一种新型的线性注意力二元视觉自回归网络架构**，预计这将进一步增强模型的能力，并推动文本到图像生成技术的边界。

由于参数量和训练数据集相对较小，建议使用常见的文本到图像模型的负面提示词 (negative prompts) 来提高生成质量。 考虑到基础模型的质量，该模型在生成准确的人体解剖结构方面可能存在局限性。 建议使用与其他文本到图像模型常用的辅助技术，例如 ADetailer，来缓解这些问题并增强细节。

**许可协议说明:** 原始仓库的许可协议未明确声明，但在此假设与此处使用的 Apache 2.0 许可协议兼容。 如果需要进一步澄清许可协议，请参考原始仓库（在“模型来源”中链接）。

- **开发者 (Developed by):** [Swarmeta-AI](https://github.com/Swarmeta-ai) & [Rath-Academy](https://github.com/RATH-Academy)
- **资助方 (Funded by):** National Supercomputing Center
- **语言 (Language(s)):** 英语 (English), 中文 (Chinese)
- **许可协议 (License):** apache-2.0
- **微调自模型 (Finetuned from model):** [Efficient-Large-Model/Sana_1600M_1024px_MultiLing](https://huggingface.co/Efficient-Large-Model/Sana_1600M_1024px_MultiLing)

### 模型来源 (Model Sources)

- **仓库 (Repository):** [https://github.com/NVlabs/Sana](https://github.com/NVlabs/Sana) (仅适用于 v0)
- **论文 (Paper):** 即将发布 (coming soon)
- **演示 (Demo):** 即将发布 (coming soon)

## 使用场景 (Uses)

### 直接使用 (Direct Use)

本模型旨在直接用于根据文本提示词生成图像，**支持英语和中文两种语言**。 用户可以利用其 **强大的指令跟随能力和长上下文窗口 (高达 1200 个 tokens)** 来创建具有详细构图和特定属性的图像。 尽管模型能力较强，但建议使用负面提示词 (negative prompts) 以进一步提升图像质量。 由于在人体解剖结构生成方面可能存在局限性，用户应注意这一点，并在生成涉及人物的图像时考虑使用 ADetailer 等技术进行改进。

### 限制使用 (Out-of-Scope Use)

本模型可能不适用于需要高度准确的人体解剖结构生成，且不使用额外优化技术的应用场景。 同样重要的是要注意基础模型可能存在的偏见和局限性，尤其是在生成与敏感话题相关的图像时。 用户应避免将此模型用于恶意目的或生成有害内容。

## 偏见、风险和局限性 (Bias, Risks, and Limitations)

与许多大型语言模型一样，本模型也可能表现出训练数据中存在的偏见。 由于模型规模和数据集较小，与更大的模型相比，它在全面理解和生成多样化且复杂的场景或概念方面可能存在局限性。 具体而言，该模型可能在准确生成人体解剖结构方面存在困难。 用户应意识到这些局限性，并批判性地评估生成的内容，尤其是在准确性和公平性至关重要的应用中。

### 建议 (Recommendations)

*   使用常见的文本到图像模型的负面提示词 (negative prompts) 以提高生成质量。
*   使用 ADetailer 等辅助技术来增强细节，并解决可能存在的人体解剖结构问题，尤其是在生成人物图像时。
*   注意模型潜在的偏见和局限性，并批判性地评估生成的内容。
*   如果对许可协议的兼容性有任何疑问，请查阅原始仓库的许可信息。


## 训练详情 (Training Details)

### 训练数据 (Training Data)

该模型在一个由 **约 6 万组精心策划的图像-文本** 组成的私有数据集上进行训练。 该数据集目前暂不公开。 未来版本将探索更广泛的数据集和新颖的训练方法。

### 速度、尺寸、时间 (Speeds, Sizes, Times) [可选]

- **模型大小 (Model Size):** 1.6B 参数 (parameters)
- **推理速度 (Inference Speed):**
    - **GPU (NVIDIA 4090):**  约 0.4 秒/张 1024x1024 图像 (Approximately 0.4 seconds per 1024x1024 image).
    - **CPU (Modern CPU):** 约 10 秒/张 2048x2048 图像 (Approximately 10 seconds per 2048x2048 image) (无 GPU - GPU-less).

## 评估结果 (Evaluation)

### 结果 (Results)


| 方法 (Methods) (1024x1024) | 吞吐量 (Throughput) (samples/s) | 延迟 (Latency) (s) | 参数量 (Params) (B) | 加速比 (Speedup) | FID 👇 | CLIP 👆 | GenEval 👆 | DPG 👆|
|-----------------------|-----------------------|-------------|------------|---------|--------|---------|----------|-------|
| FLUX-dev              | 0.04                  | 23.0        | 12.0       | 1.0×    | 10.15  | 27.47   | 0.67     | 84.0  |
| Sana-1.6B-MultiLing   | 1.0                   | 1.2         | 1.6        | 23.3×   | 5.92   | 28.94   | 0.69     | 84.5  |
| Twig-v0-alpha         | 1.0                   | 1.2         | 1.6        | 23.3×   | 5.98   | 32.92   | 0.73     | 87.2  |


**寻求支持 (Seeking Support):**  我们正在积极寻求捐赠和商业合作/赞助，以支持开源模型的开发。 捐款将用于进一步的开源模型开发。 对于商业合作/赞助，我们将优先提供专业的闭源模型、部署和支持服务。

## 联系我们 (Contact Us)

邮箱 (Email): pevernow@qq.com
