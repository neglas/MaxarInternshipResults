This is the result of my internship at Maxar technologies summer 2021.

Built a random number generator with Python script to generate realistic cities with occlusions and depth maps from a satellite perspective, potentially to be used to train a neural network to estimate depth maps.

The script generated neighborhoods of predetermined classes (city center, park, residential area, etc.) according to different probability distributions.
Cummulus/stack clouds were created with a gas simulator.
Camera was simulated by building an intrinsic camera matrix based on data from one of Maxar's satellites.
Everything was connected to an API that the user could use to determine the degree of occlusion, number of images, angles, time of day, weather, etc.



<img src="./DepthMap.gif" width="50%" height="50%"/><img src="./GeneratedCity.gif" width="50%" height="50%"/>
