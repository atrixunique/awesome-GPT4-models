**开源类GPT4多模态模型项目集合**

  1. Flamingo
   
    Laion组织(提供SD模型训练集的开源非盈利组织)根据论文用Clip与LLaMA复现了去年刷榜各种项目的的多模态模型，Flamingo相关的权重与训练代码。

    关于Flamingo的相关介绍可以看这里:https://zhuanlan.zhihu.com/p/508918171

    hugface模型仓库地址:https://huggingface.co/openflamingo/OpenFlamingo-9B

    训练代码:https://github.com/mlfoundations/open_flamingo

    模型权重净重5.2G，参数为9B，大部分人的显卡应该都能跑

    效果比Flamingo论文中的同参数下性能差一些，可能缺少某些调优吧，不过有这个效果要什么自行车！

    在线演示地址:https://7164d2142d11.ngrok.app/
    博客地址:https://laion.ai/blog/open-flamingo/


  2. Nomic AI发布的gpt4all项目


    github地址:https://github.com/nomic-ai/gpt4all

    可以跑在笔记本上，使用了800k的gpt3.5 turbo接口生成的合成文本数据集，在自指导等论文形式的帮助下训练出的LLaMA-Lora插件，项目页有Lora，数据集，训练代码等，不过因为LLaMA的学术研究性质，所以并不直接提供对应的7B LLaMA权重，这个得自己准备，性能非常不错

  3. Cerebras systems出品的Cerebras-GPT系列


    项目主页说明地址:https://www.cerebras.net/blog/ce ... ge-language-models/

    项目意义说明:https://www.businesswire.com/new ... Wafer-Scale-Systems

    arXiv论文还是coming soon
    不过hugface已经开源权重了，使用了Chinchilla缩放法则高效训练模型，授权许可为Apache 2.0
    一共公开了111m参数-13b参数总共7个版本不同的模型权重

  4. huggingface
    
    https://huggingface.co/cerebras

    4chan老哥专门有个皮格马利翁(瞧这名字)项目就是搞这个的，不过没有中文版本，最新版本都堆到6b参数了，目前来说也是开源项目，在hugface上那不是一般的火

  5. pygmalion-ai

    https://rentry.org/pygmalion-ai

    比较重复造轮子的lit-llama项目了
    因为LLaMA代码库的授权许可是GPL，这个项目通过基于nanoGPT的实现构造了一个新的Apache 2.0许可的lit-llama项目，经过这个项目转换后就可以用于商业化等措施了

    项目地址:https://github.com/Lightning-AI/lit-llama

  6. pygmalion-ai
    
    LLaMA-Adapter项目

    一看到Adapter，大部分人应该就懂了，腾讯人工智能实验室在不久前搞过一个名为T2I-Adapter的用于SD微调的附加模型，原理也来自于Adapter，通过微调附加增量参数的方法高效训练大模型的微调，并创造更多可玩性，这个项目与其是类似的，不过是用于LLM(大语言模型)方向的

    可以看到相比alpaca(斯坦福LLaMA)的全量微调，使用的参数减少到了1.2M(120万参数)，Lora大小也减少到了仅仅4.7M

    github地址:https://github.com/ZrrSkywalker/LLaMA-Adapter

  7. 不一样的
    
    前面搬了那么多LLM与多模态相关的项目，来个不一样的

    CVPR 2023论文:panic3d 单张动漫图像生成3D头部风格模型！

    github地址页:https://github.com/ShuhongChen/panic3d-anime-reconstruction

    通过使用两个大型新数据集（11.2k Vroid 3D 模型，1k Vtuber 肖像插图）训练出来的根据单张图片(你甚至可以用webui直接生成头像)并转换成3D立体头部模型

    提供有全套流程，docker，训练代码等齐全工具和说明，可以配合生成说话动作等(B站应该经常见)

  8. Japanese-Alpaca-LoRA
   
    Japanese-Alpaca-LoRA/日语 Alpaca Lora插件
    使用日文数据集训练的Alpaca Lora，可以进行日语输出

    项目说明页https://note.com/kun1emon/n/n1533345d5d26
    github地址:https://github.com/kunishou/Japanese-Alpaca-LoRA

    甚至chatGLM项目本身也有相关微调项目在进行中，综合来看其实模型最重要的还是训练集，但是这方面现在有了openai主动珠玉在前，越来越好起来了，openflamingo最重要的是开源了多模态的c4数据集

    https://github.com/mymusise/ChatGLM-Tuning
    https://github.com/ssbuild/chatglm_finetuning

  9. Luotuo

    开源的中文语言模型骆驼 (Luotuo)，该项目基于 LLaMA、Stanford Alpaca、Alpaca LoRA、Japanese-Alpaca-LoRA 等完成，单卡就能完成训练部署。

    这个模型是在 Meta 开源的 LLaMA 基础上，参考 Alpaca 和 Alpaca-LoRA 两个项目，对中文进行了训练。

    项目地址:https://github.com/LC1332/Chinese-alpaca-lora

  10. Luotuo

    ChatYuan-large-v2，元语chatAI的v2迭代版本，就是之前网上梗图那个微信小程序服务被封的那家的

    看描述开启量化之后甚至可以在手机上跑推理，开发者专门写了个gradio的ui方便交互

    github项目页:https://github.com/clue-ai/ChatYuan

    模型下载与体验地址

    https://huggingface.co/ClueAI/ChatYuan-large-v2/

    https://modelscope.cn/studios/ClueAI/ChatYuan-large-v2
----------------------------
    yswm 发表于 2023-3-29 23:11
    有什么办法本地运行让它写代码吗？


写代码国产有些专门的代码LLM大模型，比如CodeGeeX，不过需要申请才能用，而大多数的LLM，其实都有经历过代码预训练的，但这不代表一定写的好代码

https://huggingface.co/spaces/THUDM/CodeGeeX

如果你真的比较需要这方面的生产力，开个20刀的gpt4 plus或者copilot显然是更好的选择，毕竟就算本地真的跑起来了，差距也比较大


https://www.qbitai.com/2023/03/43246.html

量子位的文章，ColossalChat，又一个搭在LLaMA上的AI，有在线demo，不过


甚至中文能力极强，还有完整的RLHF微调过程，太强了

github地址:https://github.com/hpcaitech/Col ... n/applications/Chat

项目说明页:https://medium.com/@yangyou_berk ... peline-5edf08fb538b
----------------------------
Vicuna-13B，微调 LLaMA13B版本，使用ShareGPT 收集的数据集进行训练
项目主页:https://vicuna.lmsys.org/

训练集70k，来源是ShareGPT.com，效果非常不错

注:谷歌的Bard最近也被怀疑使用chatgpt的数据进行训练

更新:Vicuna开源了模型权重，这次不止训练集了

项目地址:https://github.com/lm-sys/FastChat/#vicuna-weights

除了控制台界面还有对应的gradio ui

从项目主页的说明来看，未来还会放出7b版本
----------------------------
chatGLM版的visual-chatgpt，实现原理也比较类似，readme有演示GIF

https://github.com/visual-openllm/visual-openllm
----------------------------
https://github.com/manyoso/haltt4llm

一个近期的LLM对比基准测试

在使用800k的gpt3.5turbo合成数据训练后的gpt4all(LLaMA7b微调项目)在数项测试中超越gpt3.5turbo

没想到RLHF对性能的影响已经严重到了这种程度，以至于在直接拥有微调样本的情况下可以泛化出更强的性能超越原模型

原项目中已经放出量化好的模型
https://github.com/nomic-ai/gpt4all

值得一提的是这里

把所有拒绝回答的微调样本从训练集里删了，AI就不会拒绝回答了
----------------------------
http://mp.weixin.qq.com/s?__biz= ... 771b34d0934ba4facee

ChatGLM出官方微调教程了！不过数据集还是要自己整
----------------------------
OpenChatKit出品的GPT-NeoXT-Chat-Base-20B更新到v0.16了

其实这个模型前不久才出的，数据集用了40M也就是4000万指令微调深度优化了，但当时实测起来效果并不是很好，做NLP任务还可以，对话就有点不行了，但是今天更新之后，他们专门根据对话又进行了微调，对话强了很多，虽然外语还比较差，但也有了一定程度的能力，当然最主要的还是英语能力

数据集是和Laion合作的，另外20b的模型可能看着会比较大，不过自带量化int8和cpu推理模式，也不必太过担心

演示demo:https://huggingface.co/spaces/togethercomputer/OpenChatKit

模型仓库地址:https://huggingface.co/togethercomputer/GPT-NeoXT-Chat-Base-20B
----------------------------
GPTrillion！
世界上第一个开源的万亿多模态大模型！
仓库地址:https://huggingface.co/banana-dev/GPTrillion

GPTrillion 在包含各种文本、图像和音频数据的海量数据集上进行训练。使用 BPE 算法对数据集进行预处理和标记化，并分别处理每个模态。训练过程涉及监督和无监督学习技术的组合，以自我监督的方式训练模型。

----------------------------
最近中文LLaMA微调项目也多起来了，配合llama.cpp实装的mmap高速推理，非常劲

https://github.com/ymcui/Chinese-LLaMA-Alpaca
----------------------------
新项目Baize(白泽)

demo地址:https://huggingface.co/spaces/project-baize/baize-lora-7B

github地址:https://github.com/project-baize/baize

遗憾的是目前还不怎么会中文