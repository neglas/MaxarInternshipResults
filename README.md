# Project results 
This is a small file area for interesting projects I have completed in my work life. The results are displayed as images or Gifs and are only a snippet of the final results, the results themself are a subset of many projects over the years.
The area is meant as a light version of a portfolio, to give reqqruiters an easier overview. However, if there is anything you wish to discuss please send me an email. The projects are displayed with no internal order.
Kind regards
Niclas Hansson

## Procedural Technical Intern
This is the result of my internship at Maxar technologies summer 2021.

Built a random number generator with Python script to generate realistic cities with occlusions and depth maps from a satellite perspective, potentially to be used to train a neural network to estimate depth maps.

The script generated neighborhoods of predetermined classes (city center, park, residential area, etc.) according to different probability distributions.
Cummulus/stack clouds were created with a gas simulator.
Camera was simulated by building an intrinsic camera matrix based on data from one of Maxar's satellites.
Everything was connected to an API that the user could use to determine the degree of occlusion, number of images, angles, time of day, weather, etc.

<img src="./GeneratedCity.gif" width="50%" height="50%"/><img src="./DepthMap.gif" width="50%" height="50%"/>
Left: Generated city   Right: Generated depth map
