# LALM_Acoustic_Scene_Understanding
Results of acoustic scene understanding on polyphonic soundscapes with controlled polyphony using Large Audio Language Models.

The 'usm_polyphonic_events.json' gives the different metadata information of the USM validation set and the placeholders to store the LALM responses for each audio. 
USM ID - Unique identifier for each audio clip
No. of Polyphonic Events - No. of audio classes in the audio clip.
Classes - The list of classes in the audio clip.
Loudness - The Mixing co-efficient value in dB in the same order as the list classes.
Audio Caption Ground Truth: LLM caption generation using ground truth tags.
Audio Event Tagging Question - Question prompt used for audio event tagging along with list of all USM dataset classes.
Sound Source Counting Question -  Question prompt used for counting unique number of audio classes.
Sound event Loudness ranking question - Quesiton prompt used for sorting classes based on loudest to quietest with ground truth classes of the current audio clip.

Example:

{
        "usm_id": 7,
        "no_of_polyphonic_events": 3,
        "classes": "thunderstorm, lawn mower, motorcycle",
        "loudness": "-2.208, -4.806, -15.981",
        "file_name": "7_mix.wav",
        "audio_caption_ground_truth": "A thunderstorm rumbles overhead, accompanied by the steady hum of a lawn mower in the distance.",
        "sound_event_tagging_question": "Analyze the audio and identify all the audio events by class. Provide the just the class names corresponding to each event. Choose from the following options: airplane, alarm, birds, bus, car, cheering, church bell, dogs, drilling, glass break, gunshot, hammer, helicopter, jackhammer, lawn mower, motorcycle, music, rain, sawing, scream, siren, speech, thunderstorm, train, truck, wind. Just give the class names as comma separated values string, e.g., 'class1', 'class2'. Do not include any other text or explanations.",
        "sound_source_counting_question": "Analyze how many audio unique sound events are present in the audio? Just give the number of events in number format.eg. 1, 2, 3",
        "sound_event_loudness_ranking_question": "Analyze the audio and return the classes in the order of loudest to softest sounds: motorcycle, lawn mower, thunderstorm. Just give the class names from loudest to softest. Do not inlclude any other text or explanations.",
        "audio_captioning_question": "Describe the audio as a caption in English in detail, including all the sound events present.",
        "sound_event_tagging_answer": "",
        "sound_source_counting_answer": "",
        "sound_event_loudness_ranking_answer": "",
        "audio_captioning_answer": ""
    }
