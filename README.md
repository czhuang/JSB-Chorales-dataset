# JSB-Chorales-dataset
Dataset for JSB Chorales at different temporal resolutions, with train, validation, test split from [Boulanger-Lewandowski (2012)][nicolas-data].

Three temporal resolutions are provided: quarter, 8th, 16th. They are created by choosing the pitch that is heard on the specified temporal grid.

## Example usage:
```python
import numpy as np
dataset = np.load("16th-separated.npz")
```

From Boulanger-Lewandowski (2012): "This will load a dictionary with 'train', 'valid' and 'test' keys, with the corresponding values being a list of sequences. Each sequence is itself a list of time steps, and each time step is a list of the non-zero elements in the piano-roll at this instant (in MIDI note numbers, between 21 and 108 inclusive)".

We also provide a voice-separated version, where each time step always consists of four entries that corresponds to the four voices SATB. For example, the first MIDI number is always from the Soprano voice, second from Alto, etc.  When there is a rest in a voice, a np.nan entry is used.

This dataset currently does not encode fermatas and also does not distinguish between held and repeated notes.

## References:
Boulanger-Lewandowski, N., Vincent, P., & Bengio, Y. (2012). Modeling Temporal Dependencies in High-Dimensional Sequences: Application to Polyphonic Music Generation and Transcription. Proceedings of the 29th International Conference on Machine Learning (ICML-12), 1159–1166.

[nicolas-data]: http://www-etud.iro.umontreal.ca/~boulanni/icml2012
