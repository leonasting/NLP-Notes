# Automatic Speech Recognittion
Automatic speech recognition (ASR) is a type of technology that allows computers to automatically transcribe spoken words into written text. This technology is used in a variety of applications, such as voice-to-text dictation software, speech-to-text transcription services, and voice-controlled virtual assistants.

By Source:
The task of automatic speech recognition (ASR) is to covert a waveform to a string of words

# what are the different dimensions of  Automatic Speech Recognition, Challenges and pitfalls ?
There are several different dimensions to automatic speech recognition (ASR) technology, including the following:

Acoustic modeling: This refers to the process of using statistical and machine learning techniques to model the sounds of human speech and create a map of the acoustic features of a language.

Language modeling: This involves using statistical and machine learning techniques to model the structure and grammar of a language, in order to better understand the context and meaning of the words being spoken.

Decoding: This is the process of using the acoustic and language models to convert the audio signal of spoken words into written text.

Challenges and pitfalls in ASR technology include the following:

Difficulty in recognizing words with multiple possible pronunciations or spellings (e.g. "read" and "reed").

Difficulty in recognizing words that are spoken in a noisy or unstructured environment.

Difficulty in recognizing words that are spoken with an accent or in a regional dialect.

Difficulty in recognizing words that are spoken at a fast or slow pace, or with a varying pitch or volume.

The need for large amounts of high-quality training data in order to create accurate acoustic and language models.

BY Source:

- Vocabulary dimension
    * Tasks with limited vocabulary size can be solved with very high accuracy, e.g., vocabulary of just “yes” and “no”, digit recognition (recognizing sequences of digits)
    * Open-ended tasks where videos or human conversations are transcribed are very hard (vocabulary sizes are in the range of thousands of words)
- Speech participant dimension
    * Human speaking to humans (conversational speech), e.g., transcribing a discussion or meeting, is very hard
    * Human speaking to machine or reading out loud (e.g., audio books) are relatively easy to recognize as humans seem to speak more slowly and clearly, and also use simpler words/constructs
- Channel & noise dimension
    *  Quiet space, nearby microphone vs. loud environment, far away microphone
Speaker characteristics
    * Accent, regional or ethnic dialects, child vs. adult
    * ASR not trained on the types of speakers that use the system will not perform well

# FEATURE EXTRACTION OVERVIEW

To transform the input waveform into a sequence of acoustic feature vectors (it’s like tokenization but of the waveform)
Steps:

- Sampling and Quantization Windowing
- Discrete Fourrier Transform
- Mel filter bank and log


# Explain analog to digital conversion in asr?
Analog to digital conversion is a process that involves converting an analog signal, such as a sound wave, into a digital representation, such as a sequence of binary digits (bits). This process is an essential step in many applications, including automatic speech recognition (ASR), as it allows the raw audio signal to be processed and analyzed by a computer.

In the context of ASR, analog to digital conversion typically involves the following steps:

Sampling: This step involves taking regular samples of the analog signal at a specific rate, known as the sampling frequency. The sampling rate must be at least twice the highest frequency component of the signal, in order to avoid aliasing (distortion) of the signal.

Quantization: This step involves dividing the range of the analog signal into a fixed number of levels, and assigning each sample a discrete digital value corresponding to the closest level. The number of levels used in the quantization process is known as the quantization resolution, and it determines the accuracy of the digital representation of the signal.

Encoding: This step involves converting the digital values into a binary representation, which can be stored and processed by a computer. The specific encoding scheme used will depend on the requirements of the ASR system, but common schemes include pulse-code modulation (PCM) and mu-law encoding.

The quality of the analog to digital conversion process can have a significant impact on the accuracy of the ASR system, as errors and distortions in the digital representation of the signal can make it more difficult for the system to recognize and transcribe the words being spoken.

## SAMPLING AND QUANTIZATION: ANALOG TO DIGITAL CONVERSION
**Sampling**
We measure the signal amplitude at different times based on the sampling rate we’ve chosen

- Sampling rate is number of samples taken per second
At a minimum, we need 2 samples per cycle: one to measure the positive part of the wave, and one to capture the negative part of the wave

Conversely, the max frequency wave that be measured is one whose frequency is half the sampling rate (aka Nyquist frequency)

- Most information in human speech is in frequencies below 10,000Hz and thus requires a 20,000Hz sampling rate (1 Hz is 1 cycle per) second
- Telephone speech is filtered by the switching network, so frequencies are below 4,000Hz, so an 8,000Hz sampling rate is sufficient
- Microphone speech requires 16,000Hz sampling rate
-Note that we can’t have different sampling rates for training and test data, so all data has to be downsampled to the lowest sampling rate across training and test

**QUANTIZATION**
Analog to Digital Conversion, Step 2: Quantization
We represent the real-valued sample measurements of the wave as 8 or 16 bit integers
We will use x[n] to refer to the quantized sample at time

# what is windowing in asr?
Windowing is a technique that is commonly used in automatic speech recognition (ASR) systems, in order to improve the accuracy and efficiency of the recognition process. Windowing involves dividing the raw audio signal of spoken words into overlapping segments, known as windows, and applying a window function to each segment.

The purpose of windowing is to provide a better representation of the signal, by emphasizing certain parts of the signal and de-emphasizing others. This can help to reduce the effects of noise and interference, and make it easier for the ASR system to recognize the words being spoken.

There are several different types of window functions that can be used in ASR, each with its own characteristics and advantages. Some of the most common types of window functions include the following:

Rectangular window: This is the simplest type of window function, and it involves applying a constant value to each sample in the window. This function provides good frequency resolution, but poor time resolution.

Hamming window: This window function is commonly used in ASR, as it provides a good trade-off between frequency and time resolution. It is defined by the equation:

w(n) = 0.54 - 0.46 * cos(2 * pi * n / (N - 1))

where n is the sample index, N is the window size, and pi is the mathematical constant 3.14.

Hanning window: This window function is similar to the Hamming window, but it has a smoother transition between the peak value and the zero value. It is defined by the equation:

w(n) = 0.5 - 0.5 * cos(2 * pi * n / (N - 1))

where n, N, and pi are defined as above.

Blackman window: This window function provides better frequency resolution than the Hamming or Hanning windows, but at the expense of poorer time resolution. It is defined by the equation:

w(n) = 0.42 - 0.5 * cos(2 * pi * n / (N - 1)) + 0.08 * cos(4 * pi * n / (N - 1))

where n, N, and pi are defined as above.

The specific window function used in an ASR system will depend on the requirements and goals of the system, and the characteristics of the audio signal.


By source

- Phonemes are units of sound, e.g., corresponding to pronunciation of letters
-  In order to try to extract phonemes or parts of phonemes from the digitized waveform, we use a sliding window approach to generate frames (each frame is a portion of the speech), parameterized as follows:
    * Window size (or frame size) - width in ms
    * Frame stride (or shift, or offset) between successive windows
    * Window shape, e.g., rectangular, Hamming
To extract the signal at time	, we multiply the value of the signal at time	, by the value of the window at time as follows: y[n] = w[n]s[n]

The Hamming window shrinks the values of the signal toward 0 at the window boundaries to create a more continuous signal across frames, which is better for further analysis using Fourier Transforms, and is thus more commonly used
Then we compute a Discrete Fourier transform (DFT) over the input frames, which tells us the energy at each frequency band
Outputs the magnitude and phase of the frequency components in the signal across all N discrete frequency bands


# what is  MEL FILTER BANK AND LOG?
The Mel filter bank is a type of filter bank that is commonly used in automatic speech recognition (ASR) systems, in order to improve the accuracy and efficiency of the recognition process. The Mel filter bank divides the frequency spectrum of an audio signal into a number of equally spaced bands, known as Mel-frequency bands, which correspond to the way that the human auditory system perceives frequencies.

Each Mel-frequency band is defined by a set of filters, which are applied to the audio signal in order to extract relevant features from the signal. These features are then used by the ASR system to recognize and transcribe the words being spoken.

The Mel filter bank is typically used in conjunction with a logarithmic transformation, which maps the Mel-frequency bands onto a logarithmic scale. This is because the human auditory system perceives frequencies in a logarithmic manner, and the logarithmic scale allows for a better match between the filter bank and the way that the human ear processes sound.

The Mel filter bank and logarithmic transformation are important components of many ASR systems, as they provide a more accurate representation of the audio signal and allow the ASR system to better understand the words being spoken.

By Source:

- Even though we can calculate the energy at each frequency band, human hearing is actually more sensitive to lower frequencies and ASR systems work better when they take advantage of this fact
-  We create a bank of filters that collect energy from each frequency range
    * The filter sizes are logarithmic since we want to have finer resolution at lower frequencies (e.g., the triangular filters below get larger at higher frequencies)
- The filters are multiplied by the spectrum to get a mel spectrum (mel is a unit of pitch, and the mel scale is an auditory frequency scale)
-  Then we take a log of the mel spectrum values
    * Human response to signal level is logarithmic (like human response to frequency) — humans are less sensitive at signal differences at high amplitude than they are at low amplitudes

# Explain attention based encoder decoder?

The attention-based encoder-decoder is a type of neural network architecture that is commonly used in natural language processing (NLP) and automatic speech recognition (ASR) tasks. This architecture involves two main components: an encoder, which processes the input data and extracts relevant features; and a decoder, which generates the output data based on the features extracted by the encoder.

One key feature of the attention-based encoder-decoder architecture is the use of an attention mechanism, which allows the decoder to selectively focus on different parts of the input data at different times. This allows the decoder to better capture the underlying structure and dependencies in the input data, and to generate more accurate and coherent output.

In the context of ASR, the encoder typically processes the raw audio signal of spoken words, and extracts features such as Mel-frequency cepstral coefficients (MFCC) or linear predictive coding (LPC) coefficients. The decoder then generates a sequence of words or phonemes, based on the features extracted by the encoder and the attention mechanism.

The attention-based encoder-decoder architecture has been shown to be effective in many NLP and ASR tasks, and it is a popular choice for building ASR systems that can handle large amounts of data and complex input structures.

By Source:-

Typically use encoder decoder architecture (similar to MT) Input: the log mel spectral feature vectors:
F = f1, f2, . . . , ft (one vector per 10ms frame)
Output: letters (though word pieces also used in some approaches)
Y = (⟨SOS⟩, y1, . . . . , ym ⟨EOS⟩), where	OS =	start of sequence, and EOS = end of sequence and yi ∈ {a, b, c . . . . . , z,0,....,9,⟨space⟩, ⟨comma⟩, ⟨period⟩, ⟨apostrophe⟩, ⟨unk⟩}
▸ Differences in length between input and output are a great fit for encoder-decoder architectures
However, compression/subsampling of the input is needed for ASR since the difference between input and output are too extreme
A single word is short relative to the number of frames in the acoustic feature sequence (e.g., 5-letter word can last 2s and take up 200 acoustic frames of 10ms each)
A possible compression approach known as low frame rate is to concatenate each 3 vectors together thus reducing the input length by 3 (though each input feature is 3 times longer)
