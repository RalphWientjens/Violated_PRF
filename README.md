# Violated_PRF

## A repository for a PRF experiment with violations

- This experiment is adaptation of the PRF_Experiment_Checkers by marcoaqil and uses the Exptools2 toolbox
- requirements: psychopy & exptools2

#### Usage:

Run the following line from within the experient folder.

- python main.py sub-xxx ses-x task-2R run-x

Subject SHOULD be specified according the the BIDS convention (sub-001, sub-002 and so on). Run SHOULD be an integer.

This task uses the 2R task from marcoaqil, in which the barpass has 2 squares and regular speed (20TR bar passes, aka 30 seconds with our standard sequence).

#### Settings file

In the settings file you should specify the operating system that the code is running on, as "operating system: your OS" as 'mac', 'linux' or 'windows' This is mainly important if you run the stimulus on a mac, as the size of the stimulus needs to be adjusted in that case.

You can change the task parameters in the settings file under "Task settings:"

- you can specify how much time you allow for the participant to respond that still counts as correct response (default is 0.8s), as "response interval: your time"
- you can specify the timing of the color switches (default is 3.5s), as "color switch interval: your interval" Note: Make sure that the difference between two adjacent color switches is bigger than the time you give the participant to respond. The code adds a randomization of max. +1 or -1 to the color switch times, so e.g. in case of a color switch interval of 3.5, the two closest adjacent color switches will be 1.5s apart, well outside the response interval of 0.8s.

#### Runs notebook

In the runs notebook, the runs for the participants can be computed. A standard run is made by using only horizontal and vertical barpasses. In total there are three different parts during the task:

- The standard runs part in which there are barpasses from left to right, up to down, right to left and down to up, which repeats three times.
- The same as the standard run with violations in the barpasses, where violations occur only in the orthogonal orientation, with at least two regular bar positions between violations and where all possible violation positions are used. The violations are randomly inserted and can be made for each subject individually
- The part where only the violations, that occurred in the previous part are shown, without the barpasses of the standard run.

These runs can be made by using the last function, at the bottom of the notebook. Here a name can be given to the violated run, which can be subject specific. This run will then be saved in the run_list folder in the experiment folder.
##### **Note! : Now the notebook only saves the violated part of the run, this still has to be altered to all three parts combined.**
