# phi3-Chinese
phi3以小搏大（从微软放出的跑分数据看），用不到1/2的小体积（3.8b）超越llama3 8b版性能表现，增大了在手机上部署的可行性。  
该仓库致力于收录分散在开源社区的各种phi3的训练变体版本，让更多网友发现那些不为人知的特色有趣权重。  
同时也会顺便整理phi相关训练、推理、部署的简单教程。  

## Chat模型下载
- Phi-3-mini-128k-instruct-Chinese（英文原版）：https://huggingface.co/microsoft/Phi-3-mini-128k-instruct
- Phi-3-mini-128k-instruct-Chinese
  - 增量SFT版本：
    - modelscope: https://modelscope.cn/models/baicai003/Phi-3-mini-128k-instruct-Chinese/summary
  - 直接DPO版本：待进行
  - 扩充词表版本：计划中

## 网页部署
```
streamlit run streamlit_for_instruct ./Phi-3-mini-128k-instruct-Chinese
```
<img width="1422" alt="image" src="https://github.com/CrazyBoyM/phi3-Chinese/assets/35400185/f77754e7-016b-4a66-9d8c-3e493faa11cb">


## 当前问题
- 效果与跑分不符：理想是丰满的，但我实际深度体验英文原版、以及训练中文版体验后，发现phi3-mini并没有它说的那么好用，也许它有很大的刷分嫌疑？也许对它进行叠加block操作后很有潜力？
- 32K词表过小：它的词表太小了，而且没什么中文token，经常约用3～5个token表示一个汉字，导致虽然它的体积小、加载快、运行快，但实际吐字速度比llama3 8b版还慢。也许应该对它进行词表扩充和增量预训练？ 
总体来说，我目前对它跑分超越llama3 8b的phi3-mini 3.8b版本是比较失望的，  
当然也许这个版本适合更轻量级的下游垂直任务，我们不应该以gpt3.5的水平对它抱以期待？或许做个moe版本会更好？
