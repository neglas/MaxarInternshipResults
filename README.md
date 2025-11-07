# Project results 
This is a small file area for interesting projects I have completed in my work life. The results are displayed as images or Gifs and are only a snippet of the final results, the results themself are a subset of many projects over the years. The area is meant as a light version of a portfolio, to give reqqruiters an easier overview. However, if there is anything you wish to discuss please send me an email. The projects are displayed with no internal order. 

Kind regards

Niclas Hansson


PS: I noticed some interesting artefacts in some of the GIFs due to github's compression algorithm. Clicking the ReadMe.md file to open it in a seperate view from the project main page seem better the problem, but it does not fix it completely.

## Procedural Technical Intern
This is the result of my internship at Maxar technologies summer 2021.

Built a random number generator with Python script in Blender to generate realistic cities with occlusions and depth maps from a satellite perspective, potentially to be used to train a neural network to estimate depth maps.

The script generated neighborhoods of predetermined classes (city center, park, residential area, etc.) according to different probability distributions.
Cummulus/stack clouds were created with a gas simulator.
Camera was simulated by building an intrinsic camera matrix based on data from one of Maxar's satellites.
Everything was connected to an API that the user could use to determine the degree of occlusion, number of images, angles, time of day, weather, etc.

<img src="./GeneratedCity.gif" width="50%" height="50%"/><img src="./DepthMap.gif" width="50%" height="50%"/>
Left: Proceduraly generated city   Right: Resulting depth map

## Extracting DSM from point cloud using cloth simulation 

When working at Trafikverket I had the idea to render their point cloud of the swedish road network as a mesh instead. It would serve as a startingpoint to take the bags of random points that Trafikverket had and start to hierarchialy classify them as bags of objects instead. This would save space and make it easier to use other algorithms to extract information from the dataset. The cloth simulation starts by building projecting the points into a 2D plane and extract the edges of the point cloud using a Graham Scan. A script then builds a triangular mesh with a granularity that the user can decide. Then it is just a question about moving the points while using the point cloud itself as a barrier. The visualization was done in Unreal Engine 5.1.

<img src="OldResults/DSMviaClothSim/PointCloudAndClothSim.gif" width="50%" height="50%"/><img src="OldResults/DSMviaClothSim/ClothSimResult.gif" width="50%" height="50%"/>
Left: Cloth simulation initilization  Right: Resulting DSM


## Tree Segmentation

This was at the time my longest running project at Trafikverket. There is a problem with trees falling down on railways and powerlines. Inspecting the railway routes and mark down trees which should be cut is a painfull and slow process. To aid the arborists we attached a Lidar to special built car which could drive on railways. I then did some research on methods for trunk extraction from point clouds and wrote this algorithm as well as visualized the results using Unreal Engine 5.1. The hard part was the 'wilderness' of the dataset. At the time, many algorithms that focused on trunk extraction where on cultivated forestes, where as I ahd the problem of uncultivated wild growth. An argument can be made that you can use the point cloude to create a 2.5D depth map and extract the trees py sampling the image and extract the maximum height position. However this can miss trees which are occluded or are leaning on other trees. hence I opted for a statiscal approach. Using singular value decomposition you can get an estimation of the covariance matrix to estimate each points eigenvectors based on the points in some proximity r. These eigenvectors can be used to statiscaly describe the points surroundings. Then a filter is applied based on these estimations and the trunks are extracted. After that the remaining points are put through a voxelization process to find nearby segments which highly correlates and thus probably belong to the same tree. Finally a growth process is applied by, in essence, releasing the trunk filter parameters a small step at a time and find new points in close proximity to already classified points, hence trees will start to naturaly grow outwards from the determined trunks. The algorithm performed very well and was visualized using unreal engine 5.1. The final report is added to this github project although it is in swedish.

<p align="center">
  <img src="OldResults/TreeSegmentation/Trees.png" width="75%" height="75%"/>
  
  <em>Part of original point cloud.</em>
</p>


