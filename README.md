# neurosciencehackathon2018
								=================================
								* 3rd Annual CMU NeuroHackathon *
								=================================

This hackathon was organized by researchers at BrainHub in collaboration with Carnegie Mellon University with support from Google and Phillips. 
The hackathon attracted participants from 3 CMU campuses in Doha-Qatar, Pittsburgh-USA and Kigali-Rwanda. The theme of the hackathon was "Bringing 
The Power of Machine Learning and Computer Science to Decipher Brain Function". Participants: Undergraduate and graduate-level students from a broad
range disciplines across campus: Machine Learning, Statistics, Language Technologies, Neuroscience, Psychology, and more.  

Project: What are the effects of the sleep-wake cycle on neural activity? 

Advisor: Sandy Kuhlman, Associate Professor, Biological Sciences  

Project Contributors: Yvonne Wambui, John Ibare, Samuel Wasswa, Hood Mukiibi

Project Description: 
We all know that depending on the time of day, your brain functions differently. Using Ca-imaging of neural activity in primary visual cortex of 
mice, we provide time-series data of fluorescence signal from 1,000 or so simultaneously-recorded neurons. Students will develop strategies to 
identify a relationship between neural population activity and time of day to determine whether primary sensory areas process visual information 
differently depending on the time of day.  

Description of the data set: 
Using 2-photon calcium imaging, we imaged the activity of V1 excitatory neurons in awake mice as the mice were shown 2 types of static images: 
natural scenes and sinusoidal gratings. Stimuli are presented for 1s with 2s gray screens interleaved. There are a total of 20 natural scenes 
and 60 gratings (grating stimulus set also include one gray screen control, so you will notice 61 stimuli in the grating data). One trial 
consists of the randomized presentation of each natural scene or the randomized presentation of each grating. Each mouse has its own Matlab file 
which contains two data structures, one for natural scenes and one for gratings.  

Natural_Scenes_data:
.raw_trace: trials x 1 matrix This variable provides the raw calcium signal of each cell. For a trial, each row contains a vector (neurons x frames)
 with the raw fluorescence value for a given neuron for a given frame.  

.deconv_trace: trials x 1 matrix This variable provides the deconvolved signal (estimate of spike count) of each cell. For a trial, each row 
contains a vector (neurons x frames) with the deconvolved signal value for a given neuron for a given frame.  

.stimulus_frame_index : trials x 1 matrix This variable provides which frames correspond to a stimulus vs a gray screen and the stimulus order. 
For a trial, each row contains a vector (1 x number of frames) indicating which frames correspond to gray screen and which correspond to stimuli. 
Frames are marked with either a zero (indicating gray screen) or a non-zero number (indicating a stimulus). The value of the non-zero number 
indicates which stimulus was shown.  

.isRemovedBlock: trials x stimuli matrix This variable provides which stimulus blocks should be removed due to contamination from external variables
 (too much motion when imaging, the mouse was covering its eye, running, etc.). For each trial, each stimulus receives a 0 or a 1. A 1 indicates 
that the stimulus block should be removed.  

.stimulus_shown: 1 x stimuli matrix This variable provides the natural scene images. Each cell contains the pixel value of each screen pixel. 

Gratings_data:
 This data structure follows the same setup as above. The only difference involves the stimulus shown. 

.stimulus_shown_ori: 1 x stimuli matrix This variable provides the orientation of each grating stimulus. NaN indicates the gray screen.  

.stimulus_shown_sf: 1 x stimuli matrix This variable provides the spatial frequency of each grating stimulus. NaN indicates the gray screen.
