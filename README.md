# LALM_Acoustic_Scene_Understanding
Evaluation files of acoustic scene understanding on polyphonic soundscapes with controlled polyphony using Large Audio Language Models.
The caption data in CSV file ```usm_validation_set_psuedo_captions.csv``` was obtained using LLM prompted caption generation using Qwen 2.5 7B parameter model using weakly labelled ground tags.

The ```usm_validation_set_lalm_template.json``` gives the different metadata information of the USM validation set and the placeholders to store the LALM responses for each audio. 


usm_id: Unique identifier for each audio clip.

no_of_polyphonic_events: Number of distinct audio classes present.

classes: Comma-separated list of sound event classes.

loudness: Mixing coefficient values (in dB) for each class, in the same order as classes.

file_name: Name of the corresponding audio file.

audio_caption_ground_truth: Ground truth caption using the tags.

sound_event_tagging_question: Prompt for identifying all present audio events.

sound_source_counting_question: Prompt for counting unique sound events.

sound_event_loudness_ranking_question: Prompt for ranking classes from loudest to softest.

audio_captioning_question: Prompt for generating a detailed caption.

sound_event_tagging_answer: Placeholder for LALM's tagging response.

sound_source_counting_answer: Placeholder for LALM's counting response.

sound_event_loudness_ranking_answer: Placeholder for LALM's loudness ranking response.


Example:
```
{
    "usm_id": 7,
    "no_of_polyphonic_events": 3,
    "classes": "thunderstorm, lawn mower, motorcycle",
    "loudness": "-2.208, -4.806, -15.981",
    "file_name": "7_mix.wav",
    "audio_caption_ground_truth": "A thunderstorm rumbles overhead, accompanied by the steady hum of a lawn mower in the distance.",
    "sound_event_tagging_question": "Analyze the audio and identify all the audio events by class. Provide just the class names corresponding to each event. Choose from the following options: airplane, alarm, birds, bus, car, cheering, church bell, dogs, drilling, glass break, gunshot, hammer, helicopter, jackhammer, lawn mower, motorcycle, music, rain, sawing, scream, siren, speech, thunderstorm, train, truck, wind. Just give the class names as comma separated values string, e.g., 'class1', 'class2'. Do not include any other text or explanations.",
    "sound_source_counting_question": "Analyze how many unique sound events are present in the audio? Just give the number of events in number format. eg. 1, 2, 3",
    "sound_event_loudness_ranking_question": "Analyze the audio and return the classes in the order of loudest to softest sounds: motorcycle, lawn mower, thunderstorm. Just give the class names from loudest to softest. Do not include any other text or explanations.",
    "audio_captioning_question": "Describe the audio as a caption in English in detail, including all the sound events present.",
    "sound_event_tagging_answer": "",
    "sound_source_counting_answer": "",
    "sound_event_loudness_ranking_answer": "",
    "audio_captioning_answer": ""
}
```
