# 问问AI

## 1、语音识别
1. 安装必要的库：

```
pip install pyaudio
pip install pocketsphinx
```

2. 下载语言模型：

```
wget http://sourceforge.net/projects/cmusphinx/files/Acoustic%20and%20Language%20Models/US%20English/cmusphinx-en-us-5.2.tar.gz
```

3. 解压语言模型：

```
tar -xvzf cmusphinx-en-us-5.2.tar.gz
```

4. 创建Python文件：

```
import pyaudio
from pocketsphinx import LiveSpeech

# 初始化参数
speech = LiveSpeech(
    verbose=False,
    sampling_rate=16000,
    buffer_size=2048,
    no_search=False,
    full_utt=False,
    hmm='cmusphinx-en-us-5.2/en-us',
    lm='cmusphinx-en-us-5.2/en-us.lm.bin',
    dic='cmusphinx-en-us-5.2/cmudict-en-us.dict'
)

# 开始识别
for phrase in speech:
    print(phrase)
```

5. 运行Python文件：

```
python speech_recognition.py
```

