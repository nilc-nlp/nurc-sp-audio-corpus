# NURC-SP Audio Corpus

NURC-SP Audio Corpus is a publicly available dataset for Automatic Speech Recognition (ASR) in the Brazilian Portuguese language containing 239.30 hours of audios and their respective transcriptions (170k+ segmented audios). The audios were automatically transcribed for the first time and manually revised aiming at the ASR task. 

## Metadata

- audio_name: The name given to the audio in the database. All audios extracted from the same source have the same name.
- file_path: The path to the audio file.
- text: The human-verified trancription for the given audio.
- start_time: The time the audio segment starts in the original source in seconds.
- end_time: The time the audio segment starts in the original source in seconds.
- duration: The duration of the audio segment in seconds.
- quality: Whether or not the audio had parts that could not be transcribed properly. Audios without this characteristic are rated 'high' and audios with it are rated 'low'.
- speech_genre: The speech genre of the original source of the segment. Divided into 'dialogue', 'interview' or 'lecture and talks'.
- speech_style: The speech style of the original source of the segment. All segments are categorized as 'spontaneous speech'.
- variety: The audio language. All segments are categorized as 'pt-br'.
- accent: The speaker's accent. All segments are categorized as 'sp-city'. 
- sex: The speaker's sex. Divided into 'F', 'M', 'F e F', 'F e M' and 'M e M' ('F' stands for female and 'M' stands for male). Note that some audio sources have more than one speaker, so in that case the sex refers to the main speaker or speakers.
- age_range: The speaker's age range. Divided into 'I' (25 to 35), 'II' (36 to 55) and 'III' (over 55). Note that some audio sources have more than one speaker, so in that case the age range refers to the main speaker or speakers.
- num_speakers: The number of speakers in the original source of the segment. This field was automatically writter by WhisperX, so it might not be accurate.
- speaker_id: The speaker in the segment (each different speaker in the original source was given an integer id). This field was automatically writter by WhisperX, so it might not be accurate.

## Downloads
| Hugging Face |
| ------------ |
| [Full/Filtered corpus](https://huggingface.co/datasets/nilc-nlp/CORAA-NURC-SP-Audio-Corpus) |

## Experiments:

#### 1. Wav2Vec2-NURC-SP-1

Fine-tuned version of Wav2Vec 2.0 XLSR-53. The pre-trained model was fine-tuned with our train and validation subsets of (NURC-SP Audio Corpus)  in one GPU Nvidia DGX A100 80GB for 16 epochs, with an early stop of 10. The other settings were the same from https://github.com/nilc-nlp/CORAA, training code is available at https://github.com/Edresson/Wav2Vec-Wrapper

[Model](https://huggingface.co/sidleal/Wav2Vec2-NURC-SP-1)

[Code](https://github.com/sidleal/Wav2Vec-Wrapper)

#### 2. Wav2Vec2-NURC-SP-2

This model is almost the same as (1), but using as start point the model trained for CORAA-V1 (https://github.com/nilc-nlp/CORAA) and made publicly available at https://huggingface.co/Edresson/wav2vec2-large-xlsr-coraa-portuguese

[Model](https://huggingface.co/sidleal/Wav2Vec2-NURC-SP-2)

[Code](https://github.com/sidleal/Wav2Vec-Wrapper)


#### 3. Distil-Whisper-NURC-SP

This model is a distilled version of Whisper-Large-v3 (https://openai.com/index/whisper/), a model that has support for the Portuguese language, trained using our dataset with labels determined by Whisper-Large-v3, with the reason being that more knowledge can be passed from the teacher model to the student model this way. The model was trained with our train and validation subsets of (NURC-SP Audio Corpus) in one GPU Nvidia DGX A100 80GB for 48 epochs, following to the steps given by the Distil-Whisper at https://github.com/huggingface/distil-whisper/tree/main/training

[Model](https://huggingface.co/RodrigoLimaRFL/distil-large-nurc-sp)

[Code](https://github.com/RodrigoLimaRFL/Distil-Whisper-NURC-SP-Docker)

#### 4. Distil-Whisper-NURC-SP-Fine-Tuned

This model is a fine-tuned version of (3) with our train and validation subsets of (NURC-SP Audio Corpus), following the steps recommended by the Distil-Whisper developers (https://huggingface.co/blog/fine-tune-whisper). It was also trained with 48 epochs in one GPU Nvidia DGX A100 80GB 

[Model](https://huggingface.co/RodrigoLimaRFL/distil-whisper-nurc-sp-fine-tuned)

[Code](https://github.com/RodrigoLimaRFL/Distil-Whisper-NURC-SP-Docker)

## Citation
Lima, R., Leal, S.E., Candido Junior, A., Aluísio, S.M. A Large Dataset of Spontaneous Speech with the Accent Spoken in São Paulo for Automatic Speech Recognition Evaluation. Proceedings of the 34th Brazilian Conference on Intelligent Systems (BRACIS) (2024).

````
@InProceedings{{nurc-sp-audio-corpus-2024,
    author = {Rodrigo Lima and Sidney Evaldo Leal and Arnaldo Candido Junior and Sandra Maria Aluisio},
    title = {A Large Dataset of Spontaneous Speech with the Accent Spoken in São Paulo for Automatic Speech Recognition Evaluation},
    booktitle  = {Proceedings of 34th Brazilian Conference on Intelligent Systems (BRACIS)},
    year = {2024}
}
````

## Sponsors / Funding

This work was carried out at the Center for Artificial Intelligence (C4AI-USP), with support by the São Paulo Research Foundation (FAPESP grant \#2019/07665-4) and by the IBM Corporation.  This project was also supported by the Ministry of Science, Technology and Innovation, with resources of Law No. 8.248, of October 23, 1991, within the scope of PPI-SOFTEX, coordinated by Softex and published Residence in TIC 13, DOU 01245.010222/2022-44.
