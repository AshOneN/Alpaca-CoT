[**中文**](./CN_README.md) | [**English**](./README.md)

![](./figures/宣传0.png)
# 特制自己的ChatGPT: 多接口统一的轻量级LLM-IFT平台 (**Alpaca-CoT**)
[![LICENSE](https://img.shields.io/github/license/PhoebusSi/Alpaca-CoT)](https://github.com/PhoebusSi/Alpaca-CoT/blob/main/LICENSE.txt)
[![torch](https://img.shields.io/badge/pytorch-%3E=1.13-red?logo=pytorch)](https://pytorch.org/)
[![data](https://img.shields.io/badge/huggingface-dataset-yellow?logo=data:image/png;base64,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)](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT)
[![model](https://img.shields.io/badge/huggingface-model-yellow?logo=data:image/png;base64,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)](https://huggingface.co/QingyiSi/Alpaca-CoT)
[![colab](https://img.shields.io/badge/Google-Colab-blue?logo=Google%20Colab)](https://colab.research.google.com/drive/1wfrKqyPkz5BGD1Gkij_cvbUeweIDdRav?usp=sharing)

这是Alpaca-CoT项目的存储库，该项目旨在构建一个多接口统一的轻量级指令微调（IFT）平台，该平台具有广泛的指令集合(尤其是CoT数据集)和用于各种大型语言模型以及各种参数效率方法(如LoRA，P-Tuning)的统一接口。我们正在不断扩展我们的指令调整数据收集，并集成更多的LLM。此外，我们还新建了一个分支[`tabular_llm`](https://github.com/PhoebusSi/Alpaca-CoT/tree/tabular_llm)来构造可以处理表格智能任务的大型语言模型。

<img src="./figures/image.png" width = "100" height = "100" align=right />
欢迎您向我们提供任何未收集的指令调整数据集(或其来源)。我们将统一它们的格式，用这些数据集训练羊驼模型(以及未来早期的其他LLM)，开源模型检查点，并进行广泛的实证研究。我们希望我们的项目能够为大型语言模型的开源进程做出微薄的贡献，降低其对NLP研究人员的入门门槛。

您也可以选择加入我们的群聊(WeChat)，和更多的同好研究者们交流。目前群聊人数过多，需要好友邀请才能入群，请扫码加我为好友，拉您入群。

## News
-  🚀12.8: LLM `InternLM` 已被集成进来。
- 🚀7.24 LLM `Baichuan`和`ChatGLM v2`已被集成进来。
- 🚀6.25: 新增模型评估代码，包括belle和MMCU。
- 🚀5.5: 新建了一个分支[`tabular_llm`](https://github.com/PhoebusSi/Alpaca-CoT/tree/tabular_llm)来构造可以处理多种表格智能任务的大型语言模型。
- 🚀5.4: PEFT中所有parameter-efficient方法（如P-tuning）均被集成进来，可通过超参简单设置。
- 🚀5.4: LLM `MOSS`已被集成进来。

<details><summary> 更多news </summary> 
<p>
    
- 4.21: 已收集和统一格式化数据集 `GAOKAO`, `camel`, `FLAN-Muffin`, `COIG`. 
- 4.15: 已收集和统一格式化数据集 `webGPT`, `dolly`, `baize`, `hh-rlhf`, `OIG(part)`. 
- 4.12: 现在你可以在<a href="https://colab.research.google.com/drive/1wfrKqyPkz5BGD1Gkij_cvbUeweIDdRav?usp=sharing" >Google Colab</a>中体验Alpaca-CoT.
- 4.11: 添加了`多轮对话`功能，感谢[@paulcx](https://github.com/paulcx)。
- 4.9: 已收集和统一格式化数据集 `firefly`, `instruct`, `Code Alpaca` [这里](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main).
- 4.7: 添加了`参数合并`、`本地使用`、`批量预测`、`web服务`功能，感谢[@weberrr](https://github.com/weberrr)。
- 4.4: 已收集和统一格式化数据集`FastChat`, `GPTeacher`,`Guanaco`,`HC3`,`prosocial-dialog`, `belle-chat&belle-math`, `xP3` 和 `natural-instructions`。
- 4.3: 中文的CoT数据集`CoT_CN_data.json`已上传到[这里](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main).
- 4.1: 在instinwild-CN(47k) + belle(1.5M)微调得到的Bloom7b的`checkpoint`已被上传到了[这里](https://huggingface.co/QingyiSi/Alpaca-CoT/tree/main).
- 4.1: `instnwild`（收集自推特，主要是生成、开放式QA和mind-storm types）已经被统一格式化并收集.
  
</p>
</details>




## 1. 定位

ChatGPT的出现验证了大型语言模型(LLM)在通用人工智能(AGI)上的潜力。基于LLaMA[1]等Large Language Models(LLMs)的instruction-tuning研究(如，Alpaca[2])大幅度加速了复现ChatGPT的进程。**Alpaca-CoT**希望在这个研究方向上做出适度的贡献，以推进LLMs的开源进程、降低LLMs研究和使用成本。

具体来说，**Alpaca-CoT**项目旨在探究如何更好地通过instruction-tuning的方式来诱导LLM具备类似ChatGPT的交互和instruction-following能力。为此，我们广泛收集了不同类型的instruction（尤其是Chain-of-Thought数据集），同时引入了多种参数效率方法（比如P-tuning，Qlora等8种）和LLM（比如bloom，baichuan，vicuna等多种）的接口，方便为不同的业务切换合适的方法和大模型以及数据。同时，我们对这三方面要素给出了深入细致的实证研究，以供未来工作参考。据我们所知，我们是首个将CoT拓展进Alpaca的工作，因此简称为"**Alpaca-CoT**"。


热烈欢迎您向我们提供任何未被本项目收集的instruction-tuning及各类tasks数据集（或其来源）。我们将：
- 将这些数据收录并进行统一格式化处理；
- 用这些数据集instruct fine-tune LLaMA模型（未来将集成更多LLMs），并开源其checkpoint；
- 进行广泛的实证研究以探究新收录的数据集的作用。


我们希望我们的项目能够为大型语言模型的开源过程做出适度的贡献，并降低NLP研究人员上手LLM相关研究的门槛。

## 2. 概述

![img](./figures/platform-zh.png)

近期，[LLaMA](https://arxiv.org/abs/2302.13971v1)[1]显示出惊人的zero-shot和few-shot能力，仅需较少的参数即可和GPT-3.5性能相当（LLaMA-13B显著优于GPT-3（175B），LLaMA-65B与PaLM-540MB相当），明显降低了训练、微调和使用competitive大型语言模型的成本。最近，为了提高LLaMA的instruction-following能力，[Stanford Alpaca](https://github.com/tatsu-lab/stanford_alpaca)[2]利用[self-instruct](https://arxiv.org/abs/2212.10560)[3]生成的52K Englishi nstruction-finetuning数据对LLaMA进行了微调。然而，目前该方向的研究仍然面临着以下三个挑战：
- LLaMA-7b依然对计算资源有着较高的要求；
- 用于instruction finetuning的开源数据集较少；
- 缺乏各instruction类型带来的影响的实证研究，如响应中文的能力和CoT能力。

为此，我们提出了Alpaca-CoT项目，该项目结合了相关的近期前沿技术，具有以下优势：
- 1. **_仅需要较低计算资源即可高效完成对LLaMA的微调_**。`7b`,`13b`和`30b`版本的LLaMA模型均可在单卡80G A100上轻松完成训练。该优势主要来自于[low-rank adaptation (LoRA)](https://arxiv.org/pdf/2106.09685.pdf) [4], [PEFT](https://github.com/huggingface/peft)和[bitsandbytes](https://github.com/TimDettmers/bitsandbytes)等技术。我们的代码主要修改自[这里](https://github.com/tloen/alpaca-lora)。
- 2. 我们发布的模型 **_显著提升了CoT(reasoning)推理能力_**。
- 3. 我们发布的模型 **_显著提升了对中文指令的响应能力_**。
- 4. 维护了一个仍在不断扩大规模的 **_[intruction-finetuning的数据集集合](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT)_**。该集合包含了中文、英文和CoT的instruction数据。同时，我们也维护了一个训练自各种instruction数据集的模型checkpoint集合。
- 5. 集成了 **_多种Parameter-efficient methods并统一了调用接口_**，可通过超参轻松切换。目前包含 **P-tuning, Lora**和 **Qlora**等8种方法，后续将持续加入更多,以供研究者们轻松调用和对比不同LLMs。
- 6. 集成了 **_多种LLMs并统一了调用接口_**，可通过超参轻松切换。目前包含 **LLaMA, ChatGLM**[5]和 **Bloom**[6]等10种LLMs，后续将持续加入更多,以供研究者们轻松调用和对比不同LLMs。
- 7. 提供了 **_详尽透彻的实证学习和定性分析_**，这里的findings可能会对促进未来LLM探索有一定的参考价值。



## 3. 数据集合 (Data Collection)  


收集数据集的相对大小如下图所示:

![img](./figures/show.png)


我们参考[这里](https://github.com/yaodongC/awesome-instruction-dataset) ([@yaodongC](https://github.com/yaodongC)), 将收集到的数据集按照以下规则标注Tags：

(Lang)Lingual-Tags:
- EN: Instruction datasets in English
- CN: Instruction datasets in Chinese
- ML: [Multi-lingual] Instruction datasets in multiple languages

(Task)Task-Tags:
- MT: [Multi-task] Datasets containing multiple tasks
- TS: [Task-specific] Datasets tailored for specific tasks

(Gen)Generation-method:
- HG: [Human Generated Dataset] Datasets created by humans
- SI: [Self-Instruct] Datasets generated using self-instruct methods
- MIX: [Mixed Dataset] Dataset contains both human and machine generated data
- COL: [Collection of Dataset] Dataset made from a collection of other datasets

### 数据统计
| 数据集                                                                         | 数目      | Lang         | Task      | Gen        | 类型                                                                     | 来源                                      | 链接                                                                                       |
| :----------------------------------------------------------------------------- | :------- | :----------- | :-------- | :----------| :----------------------------------------------------------------------- | :---------------------------------------- | :---------------------------------------------------------------------------------------- |
| [Chain of Thought](https://github.com/google-research/FLAN)                    | 74771    | EN/CN        | MT        | HG         | CoT相关任务                                                               | 人在现有数据集上标注CoT                    | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/Chain-of-Thought)     |
| [GPT4all](https://github.com/nomic-ai/gpt4all)                                 | 806199   | EN           | MT        | COL        | 代码，故事，对话                                                           | GPT-3.5-turbo 蒸馏                       | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/GPT4all)              |
| [GPTeacher](https://github.com/teknium1/GPTeacher)                             | 29013    | EN           | MT        | SI         | 通用，角色扮演，工具指令                                                   | GPT-4 & toolformer                        | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/GPTeacher)            |
| [Guanaco](https://huggingface.co/datasets/JosephusCheung/GuanacoDataset)       | 534610   | ML           | MT        | SI         | 多种nlp任务                                                               | text-davinci-003                         | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/Guanaco)              |
| [HC3](https://huggingface.co/datasets/Hello-SimpleAI/HC3)                      | 37175    | EN/CN        | TS        | MIX        | 对话评估                                                                  | gpt-3.5 或 人工                           | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/HC3)                  |
| [alpaca](https://github.com/tatsu-lab/stanford_alpaca)                         | 52002    | EN           | MT        | SI         | 通用指令                                                                  | text-davinci-003                         | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/alpaca)               |
| [Natural Instructions](https://github.com/allenai/natural-instructions)        | 5040134  | ML           | MT        | COL        | 多种nlp任务                                                               | 人工标注的数据集的收集                     | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/Natural-Instructions) |
| [belle_cn](https://huggingface.co/BelleGroup)                                  | 1079517  | CN           | TS/MT     | SI         | 通用指令，数学推理，对话                                                   | text-davunci-003                         | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/belle_cn)             |
| [instinwild](https://github.com/XueFuzhao/InstructionWild)                     | 52191    | EN/CN        | MT        | SI         | 生成，开放域问答，头脑风暴                                                 | text-davunci-003                         | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/instinwild)           |
| [prosocial dialog](https://huggingface.co/datasets/allenai/prosocial-dialog)   | 165681   | EN           | TS        | MIX        | 对话                                                                     | GPT-3改写问题，人工回复                    | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/prosocial-dialog)     |
| [finance_en](https://huggingface.co/datasets/gbharti/finance-alpaca)           | 68912    | EN           | TS        | COL        | 金融领域问答                                                              | GPT3.5                                   | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/)                     |
| [xP3](https://huggingface.co/datasets/bigscience/xP3)                          | 78883588 | ML           | MT        | COL        | 多种nlp任务                                                               | 人工标注的数据集的收集                     | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/xP3)                  |
| [firefly](https://github.com/yangjianxin1/Firefly)                             | 1649398  | CN           | MT        | COL        | 23种nlp任务                                                               | 收集中文数据集，人工书写指令模板            | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/firefly)              |
| [instruct](https://huggingface.co/datasets/swype/instruct)                     | 888969   | EN           | MT        | COL        | GPT4All，Alpaca和开源数据集的增强                                          | 使用AllenAI提供的nlp增强工具               | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/instruct)             |
| [Code Alpaca](https://github.com/sahil280114/codealpaca)                       | 20022    | EN           | SI        | SI         | 代码生成，编辑，优化                                                       | text-davinci-003                         | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/CodeAlpaca)            |
| [Alpaca_GPT4](https://github.com/Instruction-Tuning-with-GPT-4/GPT-4-LLM)      | 52002    | EN/CN        | MT        | SI         | 通用指令                                                                  | GPT-4 生成的Alpaca数据                    | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/alpacaGPT4)            |
| [webGPT](https://huggingface.co/datasets/openai/webgpt_comparisons)            | 18994    | EN           | TS        | MIX        | 信息检索问答                                                              | fine-tuned GPT-3 + 人工评估               | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/webGPT)                |
| [dolly 2.0](https://github.com/databrickslabs/dolly)                           | 15015    | EN           | TS        | HG         | 公开、封闭式问答、信息抽取、摘要生成、开放式构思、分类以及创意写作七类任务      | 人工标注                                  | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/dolly)                 |
| [baize](https://github.com/project-baize/baize-chatbot)                        | 653699   | EN           | MT        | COL        | Alpaca和多种问答任务                                                       | 人工标注的数据集的收集                     | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/baize)                 |
| [hh-rlhf](https://github.com/anthropics/hh-rlhf)                               | 284517   | EN           | TS        | MIX        | 对话                                                                      | RLHF models                              | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/hh-rlhf)               |
| [OIG(part)](https://laion.ai/blog/oig-dataset/)                                | 49237    | EN           | MT        | COL        | 多种nlp任务                                                               | 人工标注的数据集的收集和数据增强            | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/OIG)                   |
| [GAOKAO](https://github.com/OpenLMLab/GAOKAO-Bench)                            | 2785     | CN           | MT        | COL        | 高考中的多选，填空等问题                                                   | 人工标注的数据集的收集                      | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/GAOKAO)               |
| [camel](https://github.com/lightaime/camel)                                    | 760620   | EN           | MT        | SI         | 物理生物化学编程，数学，社会等领域的角色扮演对话人工标注的数据集的收集         | gpt-3.5-turbo 生成                        | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/camel)                 |
| [FLAN-Muffin](https://huggingface.co/datasets/Muennighoff/flan)                | 1764800  | EN           | MT        | COL        | 60种nlp任务                                                              | 人工标注的数据集的收集                      | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/FLAN-Muffin)           |
| [COIG](https://huggingface.co/datasets/BAAI/COIG)                              | 298428   | CN           | MT        | COL        | 考试，翻译，价值观指令数据集搜集，基于知识图谱的反事实对话                    | 自动化工具+人工验证                         | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/COIG)                 |
| [GPT4Tools](https://github.com/StevenGrove/GPT4Tools)                          | 71446    | EN           | MT        | SI         | a collection of tool-related instructions                               | gpt-3.5-turbo                                | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/gpt4tools)             |
| [ShareChat](https://huggingface.co/datasets/RyokoAI/ShareGPT52K)               | 1663241  | EN           | MT        | MIX        | general instruct                                                         | 收集ShareGPT                                 | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/ShareGPT)              |
| [Auto CoT](https://github.com/amazon-science/auto-cot)                         |          | EN           |           |            |                                                                          |                                            | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/Auto-CoT)              |
| [MOSS](https://github.com/OpenLMLab/MOSS)                                      | 1583595  | EN/CN        | SI        |            |                                                                          |                                            | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/MOSS)                  |
| [ultrachat](https://github.com/thunlp/UltraChat)                               | 28247446 | EN           |           |            |                                                                          |                                            | [下载](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main/ultrachat)             |
| [StackLLaMA](https://huggingface.co/datasets/lvwerra/stack-exchange-paired)    | todo     | EN           |           |            |                                                                          |                                            |                                                                                                 |


该集合仍在不断更新和扩增中。可在以下链接下载和查看更多数据细节：https://github.com/PhoebusSi/alpaca-CoT/tree/main/data



### 下载
你可以在[这里](https://huggingface.co/datasets/QingyiSi/Alpaca-CoT/tree/main)下载所有我们已经统一格式后的formatted数据。然后，将下载到的文件全部放到[data](https://github.com/PhoebusSi/alpaca-CoT/tree/main/data) folder。

你可以在[这里](https://huggingface.co/QingyiSi/Alpaca-CoT/tree/main)下载训练自各种类型instruction数据的所有checkponts。然后，在`generate.py`中的`LoRA_Weights`设置成下载路径，即可直接运行模型的inference以查看模型效果。

### 数据格式
我们集合中的所有数据均已被转化成相同的格式，每个样本的格式如下：
```
[
{"instruction": instruction string,
"input": input string, # (may be empty)
"output": output string}
]
```
注意，对于CoT数据集,我们首先使用FLAN提供的[template](https://github.com/google-research/FLAN/blob/main/flan/v2/templates.py)将其从原数据转化成Chain-of-Thought的形式，之后再统一成以上格式。格式统一化的脚本可以在[这里](https://github.com/PhoebusSi/alpaca-CoT/blob/main/data/origin_cot_data/formating.py)找到。 


## 4. 多接口统一的开源平台

### 环境配置
```
pip install -r requirements.txt
```
### 模型微调
为了便于研究者们在LLM上做系统的IFT研究，我们收集了不同类型的instruction数据，集成了多种LLM，并统一了接口，可以轻松定制化想要的搭配：
- `--model_type`: 设置想要研究的LLM，目前已支持[llama, chatglm和bloom]，其中后两者的中文能力较强，后续将会集成更多的LLMs。
- `--data`: 设置用以IFT的数据类型，以灵活特制想要的指令遵循能力，如追求较强的推理能力可设置alpaca-cot，较强的中文能力可设置belle1.5m，较强的coding和故事创作能力可设置gpt4all，金融相关的响应能力可设置finance。
- `--model_name_or_path`: 与`--model_type`相对应，用来加载目标LLM的不同型号权重。如，要加载llama的13b的模型权重时可设置decapoda-research/llama-13b-hf。 

**单卡**
- for LLaMA
```
python3 uniform_finetune.py --model_type llama --model_name_or_path decapoda-research/llama-7b-hf \
    --data alpaca-belle-cot --lora_target_modules q_proj v_proj \
    --per_gpu_train_batch_size 4 --learning_rate 3e-4 --epochs 1 
    
```

- for ChatGLM
Note: for multiple datasets, you can use `--data` like `--data ./data/alpaca.json ./data/finance.json <path2yourdata_1>`
```
python3 uniform_finetune.py   --model_type chatglm --model_name_or_path THUDM/chatglm-6b \
    --data alpaca-belle-cot --lora_target_modules query_key_value \
    --lora_r 32 --lora_alpha 32 --lora_dropout 0.1 --per_gpu_train_batch_size 2 \
    --learning_rate 2e-5 --epochs 1
```
Note that `load_in_8bit` is not yet suitable for ChatGLM, so batch_size must be much smaller than others. 

- for BLOOM
```
python3 uniform_finetune.py   --model_type bloom --model_name_or_path bigscience/bloomz-7b1-mt \
    --data alpaca-belle-cot --lora_target_modules query_key_value \
    --per_gpu_train_batch_size 4 --learning_rate 3e-4 --epochs 1 
```

- for InternLM
```
python3 uniform_finetune.py   --model_type internlm --model_name_or_path internlm/internlm-7b \
    --data alpaca --lora_target_modules q_proj v_proj --lora_r 32 --lora_alpha 32 \
    --lora_dropout 0.1 --per_gpu_train_batch_size 1 --learning_rate 2e-5 --epochs 1 \
    --compute_dtype="fp32"
```

Note that you can also pass the local path (where the LLM weights saved) to `--model_name_or_path`. And the data type `--data` can be freely set according to your interests.

**多卡**
- for LLaMA
```
python3 -m torch.distributed.launch --nproc_per_node 4  \
    --nnodes=1 --node_rank=0 --master_addr=xxx --master_port=yyy uniform_finetune.py \
    --model_type llama --model_name_or_path decapoda-research/llama-7b-hf \
    --data alpaca-belle-cot --lora_target_modules q_proj v_proj \
    --per_gpu_train_batch_size 4 --learning_rate 3e-4 --epochs 1 
```
- for ChatGLM
```
python3 -m torch.distributed.launch --nproc_per_node 4  \
    --nnodes=1 --node_rank=0 --master_addr=xxx --master_port=yyy \
    uniform_finetune.py   --model_type chatglm --model_name_or_path THUDM/chatglm-6b \
    --data alpaca-belle-cot --lora_target_modules query_key_value \
    --lora_r 32 --lora_alpha 32 --lora_dropout 0.1 --per_gpu_train_batch_size 2 \
    --learning_rate 2e-5 --epochs 1
```
Note that `load_in_8bit` is not yet suitable for ChatGLM, so batch_size must be much smaller than others. 

- for BLOOM
```
python3 -m torch.distributed.launch --nproc_per_node 4  \
    --nnodes=1 --node_rank=0 --master_addr=xxx --master_port=yyy \
    uniform_finetune.py   --model_type bloom --model_name_or_path bigscience/bloomz-7b1-mt \
    --data alpaca-belle-cot --lora_target_modules query_key_value \
    --per_gpu_train_batch_size 4 --learning_rate 3e-4 --epochs 1  
```

- for InternLM
```
python3 -m torch.distributed.launch --nproc_per_node 4  \
    --nnodes=1 --node_rank=0 --master_addr=xxx --master_port=yyy \
    uniform_finetune.py   --model_type internlm --model_name_or_path internlm/internlm-7b \
    --data alpaca --lora_target_modules q_proj v_proj --lora_r 32 --lora_alpha 32 \
    --lora_dropout 0.1 --per_gpu_train_batch_size 1 --learning_rate 2e-5 --epochs 1 \
    --compute_dtype="fp32"
```
### Inference
``` 
python3 generate.py  --data alpaca-belle-cot --model_type llama

python3 generate.py  --data alpaca-belle-cot --model_type chatglm

python3 generate.py  --data alpaca-belle-cot --model_type bloom
```

注意，`saved-xxx7b` 文件夹是保存LoRA weights的路径，而LLaMA的weights则会在脚本执行期间自动从Hugging Face上下载。

### 生成相关超参设置
```
top_p=0.9, 
        #适度调大核采样的概率阈值，扩大候选子集，增加生成多样性。
        
temperature=1.0, 
        #之前的温度参数过低会导致生成词的概率分布极化严重，导致生成策略退化成greedy decoding。
        
do_sample=True, 
        #do_sample参数默认关闭，不开启时生成仍保持beam-search解码策略，开启后为beam-search multinomial sampling解码策略。
        
no_repeat_ngram_size=6, 
        #通过配置下一个词重复出现n-gram的概率为0，来保证没有n-gram出现两次，设置过小会抑制合理的重复，影响生成的流畅性，过大会失去作用。
        
repetition_penalty=1.8, 
        #对于之前出现过的词语，在后续预测的过程中，通过引入惩罚因子repetition_penalty降低其出现的概率。
```

### 参数合并
```
python3 merge.py --model_type llama --size 7b --lora_dir xxx --merged_dir yyy
```
### 本地使用
```
python3 server.py --model_type chatglm --lora_dir xxx
```
### 批量预测
```
python3 predict.py --model_type chatglm --data for_dict_data --lora_dir xxx --result_dir yyy
```

### web服务

```
python3 web.py --model_type chatglm --lora_dir xxx
```

## 5. 中文指令微调的Empirical Study
<details><summary>注: 以下实验结果均来自于 ___An Empirical Study of Instruction-tuning Large Language Models in Chinese___.</summary>
<p>


### 5.1 评测基准（Benchmarks）
我们选择了两个评估基准，Belle-eval和MMCU，来全面评估LLM中文能力。

Belle-eval是使用ChatGPT self-instruct构建的，它有1000条不同的指令，涉及10个类别，涵盖常见的NLP任务（如QA）和具有挑战性的任务（如代码和数学）。我们使用ChatGPT根据黄金答案对模型响应进行评分。该基准评估了指令跟随能力。

MMCU是医学、法律、心理学和教育（如高考）四个专业学科的语文选择题集。它允许LLM以多项选择测试的方式参加人类社会的考试，使其适合评估LLM在多个学科中的知识广度和深度。

<p align="center">
    <img src="./figures/chinesellms-benchmarks.png" width="35%">
</p>

Belle-eval和MMCU的统计数据展示于上表。

### 5.2 主要因素
三个主要因素：基座模型（LLM Bases），参数高效方法（Parameter-efficient Methods），中文指令数据集（Chinese Instruction Datasets）。

#### 5.2.1 基座模型（LLM Bases）
针对开源LLM，我们在Belle-eval和MMCU上分别测试了现有的LLMs和在Alpaca-GPT4上使用LoRA微调的LLMs。

<p align="center">
    <img src="./figures/chinesellms-llms1.png" width="80%">
    <img src="./figures/chinesellms-llms2.png" width="40%">
</p>

表2展示了Belle-eval上开源LLMs的表现。表3展示了MMCU上开源LLMs的表现。

<p align="center">
    <img src="./figures/chinesellms-llms3.png" width="40%">
</p>

在Alpaca-GPT4上使用LoRA微调的LLMs的结果展示在图1

___实验结果：___

1. 评估现有LLMs

    ___在Belle-eval上的表现___

    (1) 对于base LLMs，Bloom表现最好。

    (2) 对于sft LLMs，ChatGLM凭借其使用最多的中文tokens和HFRL进行训练，在性能上大幅超越其他模型。
    
    (3) Open QA、Math、CloseQA和Extract类别对于现有的开源LLMs来说仍然非常具有挑战性。

    (4) Vicuna和moss-sft与它们的基础模型LLaMA和moss-base相比有明显的改善。

    (5) 相比之下，与基础模型Bloom相比，sft模型Bloomz和Bloomz-mt的性能有所下降，因为它们往往会产生较短的响应。

    ___在MMCU上的表现___

    (1) 所有基础LLM都表现不佳，因为在微调（例如输出选项号）之前，几乎很难生成指定格式的内容。

    (2) 所有sft LLM分别优于相应的基础LLM。特别是Bloomz表现最好（甚至超过了ChatGLM），得益于其监督微调数据集xP3的数据特性，它可以根据需要直接生成选项号，而不生成其他无关内容。

    (3) 在这四个学科中，法律是LLM最具挑战性的学科。

2. 指令微调不同的LLMs

    (1) 在Belle-eval上，除了sft-Bloomz和Bloomz-mt之外，指令调优带来的sft-LLM的性能提升不如基础LLM显著。

    (2) Vicuna和ChatGLM在指令调整后会出现性能下降，因为Vicuna是根据真实的人类ChatGPT对话进行训练的，质量比Alpaca-GPT4更好。ChatGLM采用了HFRL，这可能不再适合进一步的指令调整。

    (3) 在MMCU上，除了Bloomz和Bloomz-mt意外地显著降低了性能外，大多数LLM在指令调优后都实现了性能提升。

    (4) 经过指令微调后，Bloom显著改进，在两个基准测试中都表现良好。尽管ChatGLM始终击败Bloom，但在指令微调后性能下降。因此，在所有开源LLM中，Bloom最适合作为后续实验的基础模型，用于中文指令微调探索。

#### 5.2.2 参数高效方法（Parameter-efficient Methods）
针对参数高效方法，我们使用一系列参数高效方法在Alpaca-GPT4数据集上指令微调Bloom。

<p align="center">
    <img src="./figures/chinesellms-para1.png" width="40%">
    <img src="./figures/chinesellms-para2.png" width="40%">
</p>

___实验结果：___

1. 参数高效方法的对比

    (1) SadapterH在所有参数高效方法中表现最好，可以作为LoRA的替代。

    (2) P-tuning和prompt-tuning相比其他方法差距明显，这表明仅在嵌入层中添加可训练层不足以支持LLMs进行生成任务。

    (3) 尽管AdaLoRA是LoRA的改进，但其性能明显下降，这可能是因为LoRA的LLM可训练参数不适合进一步减少。

    (4) 比较上下两部分，可以看出，增加顺序适配器（即SadapterP和SadapterH）的可训练参数数量不会带来增益，而并行适配器（即P-adapter）则相反。

2. 训练损失

    (1) Prompt-tuning和P-tuning收敛最慢，收敛后损失最大。这表明仅嵌入适配器不适用于指令调优LLM。

    (2) AdaLoRA的初始损失非常高，因为它需要同时学习参数预算分配，这使得模型无法很好地拟合训练数据。

    (3) 其他方法可以在训练数据上快速收敛并很好地拟合数据。

#### 5.2.3 中文指令数据集（Chinese Instruction Datasets）
针对中文指令数据集，我们收集了开源中文指令数据集，在这些数据集上使用LoRA微调Bloom。

<p align="center">
    <img src="./figures/chinesellms-data1.png" width="80%">
    <img src="./figures/chinesellms-data2.png" width="80%">
    <img src="./figures/chinesellms-data3.png" width="40%">
</p>

表5展示了现有中文指令数据集的细节。表6和表7分别展示了Bloom对不同指令数据集的微调在Belle-eval和MMCU上的表现。

___实验结果：___

1. 在Belle-eval上的表现

    (1) 由ChatGPT构建的指令数据（例如，使用self-insturction方法或收集真实的人类-ChatGPT对话）都增强了指令跟随能力，得分提高了3.1～11点。

    (2) 在这些数据集中，Belle的性能最好，因为它的指令数据量最大。然而，在包含了更多以类似方式构造的数据的moss-sft-data上训练的模型的性能并不令人满意。

    (3) Alpaca-GPT4 指令带来的性能是次优的，大小只有 49K 却与 1.54M Belle 相当。

    (4) Instinwild 性能提升最少，因为从 Tweet（“野外”）爬取的种子指令不如人类精心设计的种子指令（比如 Alpaca）。

    (5) 这些基于ChatGPT的数据主要对开放式生成任务（如Brain Storm和generation）有显著的改进，而在阅读理解技能要求较高的任务（如Close QA和Extract）上性能显著削弱。

    (6) 基于数据集的指令数据集会损害模型的指令遵循能力，因为每个NLP任务或考试数据集的形式和意图都是单一的，很容易被过度拟合。

    (7) 其中，COIG trans表现最好，因为它涉及2000多个不同的任务，任务指令种类繁多。相比之下，xP3和COIG-ccmc对模型性能的负面影响最为严重。它们都只涉及少数类型的任务（前者涉及翻译和QA，后者涉及反事实纠正对话），几乎不涉及人类常用的指令和任务。

2. 在MMCU上的表现

    (1) 对每个数据集进行指令微调总是可以提高性能。

    (2) 在上半部分显示的基于ChatGPT的数据中，ShareGPT-zh的表现远远逊于其他数据。这可能是因为真正的用户很少提出关于学术主题的多项选择问题。

    (3) 在下半部分显示的数据集收集数据中，HC3和COIG-ccmc的准确率最低，因为HC3的唯一问题只有13K，并且COIG-ccmc的任务格式与MMCU有显著差异。

    (4) COIG-exam带来了最大的准确性提高，得益于与MMCU类似的任务格式。

### 5.3 其他因素
四个其他因素：思维链（CoT），中文词表扩充（Expansion of Chinese Vocabulary），提示语言（Language of Prompts），人类价值对齐（Human-value Alignment）。

#### 5.3.1 思维链（CoT）
针对CoT，对在指令微调中添加CoT数据前后的性能进行了比较。

___实验设置：___

文章从FLAN中收集了9个CoT数据集及其提示，然后使用谷歌翻译将其翻译成中文。比较了在指令调优过程中添加CoT数据前后的性能。

将加入CoT数据的方式记为Alpaca-GPT4+CoT”；另外，文章提出在每条指令的末尾添加一句“先思考，再决定”，以引导模型根据CoT对指令做出响应，并将这种方式记为“Alpaca-GPT4+CoT*”。

<p align="center">
    <img src="./figures/chinesellms-cot.png" width="40%">
</p>

___实验结果：___ 

1. “Alpaca-GPT4+CoT”在需要较强推理能力的Code和Math任务中表现优于“Alpaca-GPT4”。此外，MMCU Education任务也有显著提高。

2. “Alpaca-GPT4+CoT*”的简单提示进一步提高了模型在Code和Education任务中的表现，而Math中结果略低于“Alpaca-GPT4+CoT”。

#### 5.3.2 中文词表扩充（Expansion of Chinese Vocabulary）
针对中文词表扩充，文章对tokenizer词汇中的中文token数量对各种LLM在中文表达能力上的影响进行了实验。
直观地说，tokenizer词汇中的中文token数量会影响LLM表达中文的能力。

___实验设置：___

文章主要在LLaMA上进行实验。LLaMA使用的是SentencePiec（中文词汇量为32K），与Bloom（250K）相比覆盖的汉字较少。

<p align="center">
    <img src="./figures/chinesellms-voc.png" width="45%">
</p>

___实验结果：___

1. 在更多包含更丰富中文词汇的中文语料库中进行预训练，有助于提升LLM的指令跟随能力。

2. 然而，与直觉相反，在MMCU上训练的“llama-voc-pre- 1”(100B)效果比“llama-voc-pre”(20B)更差。这表明，在更多数据上进行预训练不一定能使LLM在学业考试领域上得到更好的表现。

#### 5.3.3 Prompt语种（Language of Prompts）

针对提示语言，文章对指令微调对使用中文prompts的适应性进行了实验。

<p align="center">
    <img src="./figures/chinesellms-lan.png" width="60%">
</p>

图4显示了基于LLaMA和Bloom使用中文和英文prompts的结果。当对LLaMA进行指令微调时，与英语prompts相比，使用中文prompts时均能得到更好的性能；而在Bloom上则出现了相反的现象。 

___实验结果：___

1. 对于中文能力较弱的模型（如LLaMA），使用中文prompts可以有效地帮助LLMs使用中文回答问题。

2. 对于中文能力较好的模型（如Bloom），使用英语prompts（LLMs更擅长的语言）可以更好地引导模型理解使用指令进行微调的过程。

#### 5.3.4 人类价值对齐（Human-value Alignment）
为避免LLMs生成有害内容，人类价值对齐十分重要。文章将由COIG构建的人类价值对齐数据集加入到指令微调中，针对其产生的影响进行实验。

<p align="center">
    <img src="./figures/chinesellms-human.png" width="30%">
</p>

图5展示了在指令微调中加入和没有加入人类价值对齐的结果。

___实验结果：___ 

加入人类价值对齐后，反而产生了轻微的性能下降。如何平衡LLMs的无害性和良好性能仍然需要继续探索。

</p>
</details> 

## 6. Quantitative Analysis
<details><summary>注意：下图是截止到3.26日收集到的数据集的统计情况，仅作为motivation展示。目前已收集了更多数据集，如金融相关的指令数据集。</summary>
<p>
    
![data collection statistics](https://github.com/PhoebusSi/alpaca-CoT/blob/main/figures/piechart.png)
当前的instruction-finetuning数据集合主要包含以下三个部分：
- `alpaca_data_cleaned.json`: about 52K English instruction-following training samples.
- `CoT_data.json`: 9 CoT datasets involving about 75k samples. （相关的CoT数据集由FLAN[7]发布）
- `belle_data_cn.json`:  about 0.5M Chinese |instruction-following training samples. （相关的中文instruction数据由BELLE[8]发布）

### 关于CoT和Chinese Instructions的消融
"w/o CoT" and "w/o CN" 分别表示用在instruction-finetuning期间不采用CoT数据和Chinese instructions。

需要推理能力的问题上的表现
![f3](https://github.com/PhoebusSi/alpaca-CoT/blob/main/figures/图3.png)
 
需要遵循中文指令的问题上的表现
![f4](https://github.com/PhoebusSi/alpaca-CoT/blob/main/figures/图4.png)
 
在较复杂问题上的表现
![f5](https://github.com/PhoebusSi/alpaca-CoT/blob/main/figures/图5.png)

          

**In summary, the models finetuned from our complete dataset (English, Chinese, and CoT instruction data) can significantly improve model reasoning and Chinese instruction following abilities.**


### 更多能力展示

![ablation-cot](https://github.com/PhoebusSi/alpaca-CoT/blob/main/figures/图6.png)


![ablation-cot](https://github.com/PhoebusSi/alpaca-CoT/blob/main/figures/图8.png)

</p>
</details> 



## 参考文献

[1]: [LLaMA: Open and Efficient Foundation Language Models](https://arxiv.org/abs/2302.13971v1)

[2]: [Stanford Alpaca: An Instruction-following LLaMA model](https://github.com/tatsu-lab/stanford_alpaca)

[3]: [Self-Instruct: Aligning Language Model with Self Generated Instructions](https://arxiv.org/abs/2212.10560)

[4]: [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/pdf/2106.09685.pdf)

[5]: [ChatGLM: An Open Bilingual Dialogue Language Model](https://github.com/THUDM/ChatGLM-6B)

[6]: [BLOOM: A 176B-Parameter Open-Access Multilingual Language Model](https://arxiv.org/abs/2211.05100)

[7]: [FLAN: Scaling Instruction-Finetuned Language Models](https://arxiv.org/abs/2210.11416)

[8]: [BELLE: Bloom-Enhanced Large Language model Engine](https://github.com/LianjiaTech/BELLE)

[9]: [GPT4All: Training an Assistant-style Chatbot with Large Scale Data Distillation from GPT-3.5-Turbo](https://github.com/nomic-ai/gpt4all)



## Citation
Please cite the repo if you use the data collection, code, and experimental findings in this repo. 
```
@misc{si2023empirical,
      title={An Empirical Study of Instruction-tuning Large Language Models in Chinese}, 
      author={Qingyi Si and Tong Wang and Zheng Lin and Xu Zhang and Yanan Cao and Weiping Wang},
      year={2023},
      eprint={2310.07328},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```
特别鸣谢：感谢APUS AilMe研究院为我们的实验赞助的8张A100。
