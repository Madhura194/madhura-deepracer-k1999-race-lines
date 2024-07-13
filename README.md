# Title

This repo is fork created out of https://github.com/cdthompson/deepracer-k1999-race-lines and modified and added raceline calculation and action space for Ross Raceway track 

This requires below environments and dependences setup in system

Python
Vscode
Anaconda
pip/pip3

Libraries 

pip install numpy
pip install shapely
pip install pandas
pip install matplotlib
pip install scipy
pip install seaborn
pip install sklearn

To get more details about how to set this up locally .
Please refer below blogpost: https://www.linkedin.com/pulse/aws-deepracer-how-calculate-best-racing-line-compute-actions-chen/


# Discovering Race Lines in DeepRacer Track Geometries


The [AWS DeepRacer Virtual Circuit](http://deepracerleague.com) is run every month and uses reinforcement learning to teach a car to successfully navigate a race track.  

Rewards functions are developed by each competitor in order to guide the learning, and these functions can vary widely.  One of the experiments I wanted to try was to be overly prescriptive to the car.  


## Source and Result

| Original Track | Calculated Race Line | Numpy coordinates |
|----------------|----------------------|-------------------|
| ![](assets/Canada.png) | ![](assets/Canada_Race.png) | NumPy:&nbsp;[Canada_Training](racelines/Canada_Training-1000-4-2019-10-11-163418.npy) Python&nbsp;Code:&nbsp;[Canada_Training.py](racelines/Canada_Training-1000-4-2019-10-11-163418.py) |
| ![](assets/reinvent.png) | ![](assets/reinvent_race.png) | NumPy:&nbsp;[reinvent_base.npy](racelines/reinvent_base-400-4-2019-10-11-161903.npy) Python&nbsp;Code:&nbsp;[reinvent_base.py](racelines/reinvent_base-400-4-2019-10-11-161903.py) |
| ![](assets/reinvent2019.png) | ![](assets/reinvent2019_race.png) | NumPy:&nbsp;[reinvent2019.npy](racelines/reInvent2019_track-1000-4-2019-11-09-113228.npy) Python&nbsp;Code:&nbsp;[reinvent2019.py](racelines/reInvent2019_track-1000-4-2019-11-09-113228.py)



## Method

Borrowed directly from [Rémi Coulom's PhD Thesis](https://www.remi-coulom.fr/Thesis/):

> ![](assets/algorithm.png)

The code was hastily written but achieved a good enough result, so I stopped improving it.  One limitation is that the points along the race line will never migrate in the opposite direction of curvature, leaving some room for further straightening of the race line.
