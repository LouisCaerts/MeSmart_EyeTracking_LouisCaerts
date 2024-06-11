# MeSmart_EyeTracking_LouisCaerts

## A repository containing my combined work while at UZH IRM.


### TODO
* Add a "section 0" that talks about the kind of data that was available (the input) and the problems that might arise from it, the expectations in the beginning, the sources referenced, brief introduction, ...
* NEW DIVISION OF STEPS
    * STEP 0 ==> Introduction, what kind of data, anticipated challenges, goals, expectations, ...
    * STEP 1 ==> Basic code + experimentations with it 
    * STEP 2 ==> Justifying the non-edited videos (5-mins video comparisons)
    * STEP 3 ==> Edit code for longer videos and more of them ==> problem with threshold ==> same comparison but with 15-min video (+tests with various threshold calculations) ==> finish with threshold calculation method choice
    * STEP 4 ==> Full analysis of database and potential problem ==> Full dataframe with descriptions of results, post-processing, ... full discussion of dataframe: how well did previous decisions turn out? Can it even be better?
    * STEP 5 ==> Actual data analysis + modelling (exploratory + GLM)
    * STEP 6 ==> Potential publication (work in progress, don't bother with this for now)
    * STEP 7 ==> Full codebase for future reuse (kinda separate)

  

### Introduction

In light of the MeSmart study, I mostly worked on extracting eye-related data from video files. This was done only for videos of participants made before the department had access to eye-tracking goggles (TOBY glasses). This repository serves as both a database of all of the work that I have done (minus any sensitive data) as well as a step-by-step guideline of how to read/use it for anyone who might need to in the future. I have structured it in a way that reflects the process of working on it. I will briefly describe all sections here. For more detailed information about each of those sections, simply navigate to the corresponding folder in this repository.

Please note that the majority of the time I will speak of "blink detection", "blinking data", "eye data", etc. However, the process of yawn detection, yawning data, mouth data, ... was always happening in a parallel and analogous fashion.

### 1. Automated blink detection
The original purpose of my work, as mentioned above, was to attempt to extract eye-related data from old recordings of people using the VICTOR driving simulator. This was needed since eye-tracking glasses were not available at the time. The eventual goal, if succesful, would then be to see if this eye data could be correlated to sleepiness behind the wheel in some way. The first step in this process was to actually get the blink detection working. This sections covers all the steps I took and things I tried during this phase. This also covers sources I used, different versions of frameworks that were tried out and various attempts at improving the output with video pre-processing.

### 2. Feasibility of using automated blink detection
After the initial blink detection was working, it was worth asking the question if using it was actually the best option for what we were trying to achieve. In particular, since the MeSmart videobase is limited in size (and since eye-tracking glasses would be available for future VICTOR drives) we wanted to test if it would perhaps be more efficient to simply write down the blinking data manually for all of the videos. This section describes a small experiment where video samples whose manual and automatic blink detections were compared in order to determine if the automatic blink detection algorithm was (a) accurate enough to feasibly use, and (b) large enough of a time saver to make up for any loss of accuracy that might occur.

### 3. Video file to blinking data pipeline
Once it was established that it was worth to use the automated blinking analysis to analyze the MeSmart videobase, the next qustion became how to do so. This section describes the process of setting up pipeline that automates as many of the steps as possible to go from original video files to a final dataset. This was done to make the process less time intensive in case it needs to be repeated in the future and to minimize the potential for human error. It includes wrapping the blink detection code in a larger program that automatically reads and outputs data from/to the correct files and also describes the naming conventions and potential uses of all those output files.

### 4. MeSmart study videobase analysis
Once the pipeline for processign the video files was set up, the MeSmart videobase was run through it. This section describes that resulting the database, the post-processing steps that were performed on it, and also the various forms of analysis used to extract information from it. 

### 5. Finalization, work summarization, and potential publication attempt
WORK IN PROGRESS
