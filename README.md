# NURC-SP Corpus

NURC-SP Corpus CORAA ASR is a publicly available dataset for Automatic Speech Recognition (ASR) in the Brazilian Portuguese language containing 239.68 hours of audios and their respective transcriptions (170k+ segmented audios). 

The audios were either validated by annotators or transcripted for the first time aiming at the ASR task.

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
- accent: The speaker's accent. All segments are categorized as 'sp-city'. Note that some audio sources have more than one speaker, so in that case the accent refers to the main speaker or speakers.
- sex: The speaker's sex. Divided into 'F', 'M', 'F e F', 'F e M' and 'M e M' ('F' stands for female and 'M' stands for male). Note that some audio sources have more than one speaker, so in that case the sex refers to the main speaker or speakers.
- age_range: The speaker's age range. Divided into 'I' (25 to 35), 'II' (36 to 55) and 'III' (over 55). Note that some audio sources have more than one speaker, so in that case the age range refers to the main speaker or speakers.
- num_speakers: The number of speakers in the original source of the segment. This field was automatically writter by WhisperX, so it might not be accurate.
- speaker_id: The speaker in the segment (each different speaker in the original source was given an integer id). This field was automatically writter by WhisperX, so it might not be accurate.

## Downloads
| Hugging Face |
| ------------ |
| [Download Link]() |

## Citation

## Partners / Sponsors / Funding

## References
