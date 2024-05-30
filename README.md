# AudioLlama
## 项目简介
这个项目实现了一个简单的语音对话机器人，能够进行自然语言理解和语音交互。该机器人利用语音处理技术和大语言模型，包括语音识别、语音合成和主动型Agent, 为用户提供了实时语音交互体验。此外，机器人还具备基于检索的问答和工具调用功能，提升了交互的智能性和实用性。项目由以下三个主要组件构成:
1. ASR: 端到端语音识别系统, 用于将用户语音输入转写为文本作为语言模型输入。
2. ChatBot: 基于LLM的对话机器人, 可智能地根据用户输入进行选择闲聊、检索回答或工具调用功能。
3. TTS: 语音合成系统，对话系统的输出文本合成为普通话语音并可以与文本同时进行流式输出。

## 功能介绍
### ASR
该项目的语音识别系统是使用 ESPnet 开源工具包训练的一个端到端语音识别模型。使用 LoRA 在中文语音转写数据集上微调的 Whisper 模型实现高精度的普通话语音转写。
1. Toolkit: ESPnet https://github.com/espnet/espnet
2. Dataset: AIShell https://www.openslr.org/33/
3. ASR Model: Whisper https://github.com/openai/whisper 
### ChatBot
聊天机器人是基于 Chinese-Llama3 Instruction 版本构建的, 在此基础上使用 Langchain 构建了一个主动型 Agent, 可以根据用户输入进行自主决策采用的行为以便更智能化地回答用户问题。
### TTS
语音合成系统采用是使用ESPnet工具包训练的端到端的语音合成模型, 模型架构采用的是 FastSpeech2 + HifiGAN, 使用的是 JETS 训练方法从而避免了传统二阶段语音合成系统 mel 谱 miss match 的问题。
