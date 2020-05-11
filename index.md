<link href="style.css" rel="stylesheet">


# Overview
Our method allows to learn continuous high-level controls from simple annotations in symbolic music generation.
In this page, we show additional experimental results for 13 attributes, audio samples and feature 
explanations from the official [webpage](http://jmir.sourceforge.net/manuals/jSymbolic_manual/home.html). 

- [Single attribute](#single-attribute)
- [Double attributes](#double-attributes)
- [Triple attribute](#triple-attributes)

# Single attribute
## Total number of notes
Total number of notes, including both pitched and unpitched notes.

## Pitch variability
Standard deviation of the MIDI pitches of all pitched notes in the piece. Provides a measure of how close the pitches 
as a whole are to the mean pitch.

## Rhythmic value variability
Standard deviation of the note durations in quarter notes of all notes in the music. Provides a measure of how close the 
rhythmic values are to the mean rhythmic value. This calculation includes both pitched and unpitched notes, is 
calculated after rhythmic quantization, is not influenced by tempo, and is calculated without regard to the dynamics, 
voice or instrument of any given note.

## Pitch kurtosis
Kurtosis of the MIDI pitches of all pitched notes in the piece. Provides a measure of how peaked or flat the pitch 
distribution is. The higher the kurtosis, the more the pitches are clustered near the mean and the fewer outliers there 
are.

##  Pitch skewness
Skewness of the MIDI pitches of all pitched notes in the piece. Provides a measure of how asymmetrical the pitch 
distribution is to either the left or the right of the mean pitch. A value of zero indicates no skew.

## Prevalence of most common rhythmic value
The fraction of all notes that have a rhythmic value corresponding to the most common rhythmic value in the music. 
This calculation includes both pitched and unpitched notes, is calculated after rhythmic quantization, is not influenced 
by tempo, and is calculated without regard to the dynamics, voice or instrument of any given note.

## Average note duration
Average duration of notes (in seconds).

## Note density variability
How much the note density (average number of notes per second) varies throughout the piece. Takes into account all notes 
in all voices, including both pitched and unpitched notes. In order to calculate this, the piece is broken into windows 
of 5 second duration, and the note density of each window is calculated. The final value of this feature is then found 
by calculating the standard deviation of the note densities of these windows. Set to 0 if there is insufficient music 
for more than one window.

## Amount of arpeggiation
Fraction of melodic intervals that are repeated notes, minor thirds, major thirds, perfect fifths, minor sevenths, 
major sevenths, octaves, minor tenths or major tenths. This is only a very approximate measure of the amount of 
arpeggiation in the music, of course.

## Chromatic motion
Fraction of melodic intervals that correspond to a semitone.

## Direction of melodic motion
Fraction of melodic intervals that are rising in pitch. Set to zero if no rising or falling melodic intervals are found.

## Average interval spanned by melodic arcs
Average melodic interval (in semitones) separating the top note of melodic peaks and the bottom note of adjacent melodic 
troughs. Similar assumptions are made in the calculation of this feature as for the Melodic Interval Histogram.

## Chord duration
Average duration a chord in units of time corresponding to the duration of an idealized quarter note. A "chord" here is 
considered to stay the same as long as no new pitch classes are added, and no pitch classes are taken away. 
This "chord" may consist of any number of pitch classes, even only one. A "chord" is not considered to end if it is
split by one or more rests (although the rests themselves are not counted in the duration of the "chord").

# Double attributes
In this section, two attributes are trained at the same time.

## Total number of notes & pitch variability

|↓Less total number of notes↓|→More pitch variability→||
|:-:|:-:|:-:|
|<img src="figs/total_pitch/reels_simple_chords_418.mid_2_0.png"><br><audio controls><source src="mp3/total_pitch/reels_simple_chords_418.mid_2_0.mp3"></audio>|<img src="figs/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_1.3244_Pitch_Variability_-0.17049.png"><br><audio controls><source src="mp3/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_1.3244_Pitch_Variability_-0.17049.mp3"></audio>|<img src="figs/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_1.3244_Pitch_Variability_0.82951.png"><br><audio controls><source src="mp3/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_1.3244_Pitch_Variability_0.82951.mp3"></audio>|
|<img src="figs/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_0.32442_Pitch_Variability_-1.1705.png"><br><audio controls><source src="mp3/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_0.32442_Pitch_Variability_-1.1705.mp3"></audio>|<img src="figs/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_0.32442_Pitch_Variability_-0.17049.png"><br><audio controls><source src="mp3/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_0.32442_Pitch_Variability_-0.17049.mp3"></audio>|<img src="figs/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_0.32442_Pitch_Variability_0.82951.png"><br><audio controls><source src="mp3/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_0.32442_Pitch_Variability_0.82951.mp3"></audio>|
|<img src="figs/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_-0.67558_Pitch_Variability_-1.1705.png"><br><audio controls><source src="mp3/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_-0.67558_Pitch_Variability_-1.1705.mp3"></audio>|<img src="figs/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_-0.67558_Pitch_Variability_-0.17049.png"><br><audio controls><source src="mp3/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_-0.67558_Pitch_Variability_-0.17049.mp3"></audio>|<img src="figs/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_-0.67558_Pitch_Variability_0.82951.png"><br><audio controls><source src="mp3/total_pitch/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_-0.67558_Pitch_Variability_0.82951.mp3"></audio>|

## Total number of notes & rhythmic value variability

|↓Less total number of notes↓|→More rhythmic value variability→||
|:-:|:-:|:-:|
|<img src="figs/total_rhythm/reels_simple_chords_418.mid_2_0.png"><br><audio controls><source src="mp3/total_rhythm/reels_simple_chords_418.mid_2_0.mp3"></audio>|<img src="figs/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_1.3244_Rhythmic_Value_Variability_-0.76632.png"><br><audio controls><source src="mp3/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_1.3244_Rhythmic_Value_Variability_-0.76632.mp3"></audio>|<img src="figs/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_1.3244_Rhythmic_Value_Variability_0.73368.png"><br><audio controls><source src="mp3/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_1.3244_Rhythmic_Value_Variability_0.73368.mp3"></audio>|
|<img src="figs/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_0.32442_Rhythmic_Value_Variability_-1.2663.png"><br><audio controls><source src="mp3/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_0.32442_Rhythmic_Value_Variability_-1.2663.mp3"></audio>|<img src="figs/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_0.32442_Rhythmic_Value_Variability_-0.76632.png"><br><audio controls><source src="mp3/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_0.32442_Rhythmic_Value_Variability_-0.76632.mp3"></audio>|<img src="figs/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_0.32442_Rhythmic_Value_Variability_0.73368.png"><br><audio controls><source src="mp3/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_0.32442_Rhythmic_Value_Variability_0.73368.mp3"></audio>|
|<img src="figs/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_-0.67558_Rhythmic_Value_Variability_-1.2663.png"><br><audio controls><source src="mp3/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_-0.67558_Rhythmic_Value_Variability_-1.2663.mp3"></audio>|<img src="figs/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_-0.67558_Rhythmic_Value_Variability_-0.76632.png"><br><audio controls><source src="mp3/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_-0.67558_Rhythmic_Value_Variability_-0.76632.mp3"></audio>|<img src="figs/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_-0.67558_Rhythmic_Value_Variability_0.73368.png"><br><audio controls><source src="mp3/total_rhythm/reels_simple_chords_418.mid_2_0_demo_Total_Number_of_Notes_-0.67558_Rhythmic_Value_Variability_0.73368.mp3"></audio>|

## Total number of notes & chromatic motion

## Pitch variability & rhythmic value variability

## Pitch Variability & chromatic motion

## Rhythmic value variability & chromatic motion

# Triple attributes
In this section, three attributes are trained at the same time.

## Total number of notes, pitch variability & rhythmic value variability

## Total number of notes, pitch variability & chromatic motion
