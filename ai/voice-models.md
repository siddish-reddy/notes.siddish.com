---
description: Native → Text + Speech as Input and Text + Speech as Output;
icon: book-blank
---

# Voice Models

{% hint style="info" %}
WIP still, catching up with current open/commercial options and references to DIY
{% endhint %}

Current Cascading Approach: VAD →  ASR → LLM → TTS

Has problems:

* Interruptions
* First word Latency
* Cascading of errors from VAD/ASR
* emotion, tone, and other speech features are lost

### State of the Art:

#### Full Duplex Models (end to end continuous speech in/out):

[Moshi.chat](https://moshi.chat) by Kyutai (pending open source/API release)

[LSLM](https://ziyang.tech/LSLM/) (Language Model Can Listen While Speaking) by ByteDance

#### Turn Based Models with Speech as Input:

[Ultravox](https://github.com/fixie-ai/ultravox) 0.4 by Fixie

[Qwen2-Audio-Chat](https://qwenlm.github.io/blog/qwen2-audio/) by Qwen Team, Alibaba (Whisper encoder to embed melspectrogram, then use it as prefix to LLM)

[AnyGPT](https://junzhan2000.github.io/AnyGPT.github.io/)/[SpeechGPT](https://0nutation.github.io/SpeechGPT2.github.io/)2

[llama-3-s](https://homebrew.ltd/blog/llama3-just-got-ears)

[Gazelle](https://github.com/tincans-ai/gazelle?) [0.2](https://tincans.ai/slm3) by Tincans

[Shuka v1 by Sarvam (Indic)](https://www.sarvam.ai/blogs/shuka-v1)

GPT-4o voice by OpenAI

***

[Yet to read](https://arc.net/folder/D69A3992-3BE8-40D4-8701-3E6157C9F409) papers folder

[People to follow](https://x.com/i/lists/1826735005298729464) ( X.com list)

### Notes

Cascading Approach

minimum latency: 500ms on cloud via

VAD: [silero-vad](https://github.com/snakers4/silero-vad) on edge/onnx

ASR: whisper via Groq

LLM: Llama via Groq

TTS: [Sonic](https://cartesia.ai/sonic) by Cartesia

Or Locally via modular [HF pipeline](https://github.com/huggingface/speech-to-speech)



Ultravox → LLama3 + Whisper Encoder, plans on full duplex, API in beta

Gazelle -> Mistral 7b instruct + wav2vec2 + DPO, API in waitlist



The speech signals are encoded into discrete tokens, and then discrete speech tokens are expanded into the vocabulary of the LLM\


[LSLM](https://ziyang.tech/LSLM/) architecture

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdEUfKaddpyzl_g6dZbjaclGtM-gEXYWJKsxf1CXELtpHjxKadmm74gDFdAGJRlsN4Qw3XnTVHbNpauRrB6g7iPc4alIxz0FLu1ULeWB_Edya466IU4F1evW51BCjXDThui8XZp8ABK3spu39P_hLr7ILQ?key=g3jZRcP1xgntv30Siq4dbQ" alt=""><figcaption></figcaption></figure>



Speech/Text to Speech/Text:

non dialogue tasks: LauraGPT, Viola, VoxtLM\


<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcuG0XJ2cOot6WOt1EoU6VoPpazAz14eDDR9HIcVT3z5y0GeyXXJ2eLElGEUcVPrC6e0cemNEv8vQeAsM9doq_8qXhLBofvQjfpXvaJEL0L4MYwYwlHqA5z_QWMkyGRviYQwlDccJesn9nlBMOdOYPDbloK?key=g3jZRcP1xgntv30Siq4dbQ" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfV1V45aF4fVJk1wjIcPxwAkICzkFzMoWrumC4CNIww4y6hodA2H6OyTdKXOfsoXY4uKLgl-mv6ui_yt-lBipGjvIRtvyvCfz6B6cbC2Xb4ifMxx2p2B8zYpZF10BVSYRgC1MXWbW2wOvcm8ujOku8N4qA?key=g3jZRcP1xgntv30Siq4dbQ" alt=""><figcaption></figcaption></figure>

**Speech/Text to Text:**

* Encoder + Adapter style models: Following the manner of LLaVA, we leverage the well-trained speech modal encoder and the LLM, which makes LLaSM more resource-friendly. Specifically, we use Whisper as a speech encoder to encode the speech signals into embeddings. Then a modal adaptor learns to align speech embeddings with the input text embeddings of the large language model. The speech embeddings and the text embeddings are concatenated together to form interleaved sequences, then the interleaved sequences are input to the LLM for supervised fine-tuning. The training process is divided into two stages. In the first stage, we use the public ASR datasets for the modality adaptation pre-training. The speech encoder and the LLM are frozen, only the modal adaptor is trained to align the speech and text embeddings. As most of the model parameters remain frozen, only a small part of the parameters from the modal adaptor is trained during this stage, it is not resource-consuming. In the second stage, we use cross-modal instruction data for training to provide the model with the capacity to process cross-modal conversations and handle multi-modal instructions. The speech encoder is frozen while the parameters of the modal adaptor and the language model are updated for cross-modal instruction fine-tuning.

[Qwen2-Audio-Chat](https://qwenlm.github.io/blog/qwen2-audio/) (latest)

[WavLLM](https://arxiv.org/abs/2404.00656) by Msft\
[SenseVoice](https://github.com/FunAudioLLM/SenseVoice) (90 ms)\
[Audio Flamingo](https://audioflamingo.github.io/) (dialogue trained, tiny base model though)

[GAMA Audio\
](https://sreyan88.github.io/gamaaudio/)[LTU-AS](https://github.com/YuanGongND/ltu),\
Salmon\
[LLaSM](https://github.com/LinkSoul-AI/LLaSM),\
COSMIC

*

    <figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXd8OBLeHcyri5y3G0wTGbwktGMUBh6rlsfz0_pHGOBl7TNUldoGVWXq_6LeCISK0IWJ-qMxeVFhSGjVxrhMeswlKDnf0Q-DWDy_wlJbQE6PfXB9WqqXcbCLMDyFpYVEF_MUbev4FsGN5mWuFEk1U5vr6As?key=g3jZRcP1xgntv30Siq4dbQ" alt=""><figcaption></figcaption></figure>
*

    <figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXc_FBklTtxyvXAIfPesf9ekEbMWhRphHDaN815mCtj2bcUUE9FIK1RaamsL-JK2XRgagGpfArK2GKp0v38yGYeuPMBHLgJGGZSkD6tSIQ5bFqZk1CRP1VBVe-Rf79XaaxhMjzdTXoNDzXeBKdBfhNmvaRM?key=g3jZRcP1xgntv30Siq4dbQ" alt=""><figcaption></figcaption></figure>
*

    <figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcNVZPhLCM6rBEe6yPWKyUkFPJcTKnpaihqepncP0e-6dcphKlgm4RwtRAm0kdX1lCORKJxcep9gGxbnm0XovaSUXOu_OfkKhJ8-qMAVCO_zd1hnZdMlyVPJpcUs3tmN1oni-iy63dvLgxrD2uywrcvH_zr?key=g3jZRcP1xgntv30Siq4dbQ" alt=""><figcaption></figcaption></figure>



VIsion Language Models

* Palm-E: 540B PaLM + 22B Vision Transformer
* LLaVA: pre-trained CLIP visual encoder + LLaMA and instruct tuning on GPT4-assisted visual instruction data.
* BLIP-2: Flan-T5 with a Q-Former to align visual features with the LM\


Cascading Models:

* [Parler-tts](https://github.com/huggingface/parler-tts): high-quality, natural sounding speech with features that can be controlled using a simple text prompt (e.g. gender, background noise, speaking rate, pitch and reverberation) and [consistent voices](https://huggingface.co/parler-tts/parler-tts-mini-expresso).
