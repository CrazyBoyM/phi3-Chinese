# phi3-Chinese
phi3以小搏大，用不到1/2的小体积（3.8b）超越llama3 8b版性能表现，增大了在手机上部署的可行性，几乎标志着大规模开启AI in 手机、AI in PC的端侧时代。  
该仓库致力于收录分散在开源社区的各种phi3的训练变体版本，让更多网友发现那些不为人知的特色有趣权重。  
同时也会顺便整理phi相关训练、推理、部署的简单教程。  

## Chat模型下载
- Phi-3-mini-128k-instruct-Chinese（英文原版）：https://huggingface.co/microsoft/Phi-3-mini-128k-instruct
- Phi-3-mini-128k-instruct-Chinese
  - 增量SFT版本：
    - modelscope: https://modelscope.cn/models/baicai003/Phi-3-mini-128k-instruct-Chinese/summary
  - 直接DPO版本：待进行
  - 扩充词表版本：计划中

## 当前问题
- 效果与跑分不符：理想是丰满的，但我实际深度体验英文原版、以及训练中文版体验后，发现phi3-mini并没有它说的那么好用，也许它有很大的刷分嫌疑？也许对它进行叠加block操作后很有潜力？
- 32K词表过小：它的词表太小了，而且没什么中文token，经常约用3～5个token表示一个汉字，导致虽然它的输出体积、运行快，但实际吐字速度比llama3 8b版还慢。也许应该对它进行词表扩充和增量预训练？  
总体来说，我目前对它跑分超越llama3 8b的phi3-mini 3.8b版本是比较失望的，但如何它的后续版本（7b）效果确实ok（而不是在做题任务上定向刷分），我会接着维护这个仓库。
