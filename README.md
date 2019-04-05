# deep voice论文学习
## 系统结构

![](https://github.com/sysu16340234/deep_voice_learning/blob/master/imgs/deep_voice.png)

系统包含五个基本模块:**字素转换音素模型,分割模型,音素持续时间模型,基频模型,音频合成模型**:

* **字素转换音素模型**:用来将文本转化为音素
* **分割模型**:分割模型用来识别给定音频中每个音素的边界,即开始和结束的位置
* **音素持续时间模型**:用来预测音素序列中每个音素的持续时间
* **基频模型**:预测音素是否为浊音,如果是浊音，则在在音素的持续时间过程中预测基频;
* **音频合成模型**:组合了字素转换音素模型,音素持续时间模型,基频模型,以高采样率生成所需文本的音频;

**训练过程**:给定音频和对应文本,将文本通过G2P模型转换为音素,将音素和音频输入分割模块,使用分割模块将音素的边界作标记即得到音素持续时间,将音素持续时间,音素和音频输入音频合成模型作为训练样本,将持续时间和音素输入持续时间模型作为训练样本,对音频进行基频提取,然后将基频和音素输入基频模型作为训练样本;

**推理过程**:文本经过字素转换音素模型或者使用音素字典转换成音素,再把音素提供给音素持续时间模型和基频模型预测每个音素的持续时间和基频,最后将基频和音素持续时间作为局部条件特征输入音频合成模型,音频合成模型使用这两类特征和音素合成音频;

