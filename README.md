[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=http%3A%2F%2Fbibeklalkarn.github.io%2FMoonShakers%2F&count_bg=%233DABC8&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://hits.seeyoufarm.com)
# MoonShakers
MoonShakers is an interactive 3D lunar globe on a web app using globe.gl API and used seismic geophysical data transmitted back to Earth by several instruments left behind by NASA’s Apollo astronauts. Specifically, we used dataset named nakamura_1979_sm_locations.csv. We added data on points layer and attached ripple effect at each point to show moonquake propagation. The datasets we used contained a total of 28 moonquake locations with their times. We have taken the magnitude instead of the depth of such waves. Our approach might help people seek a greater view using a 3d digital lunar globe and seismic waves using color concentration. We have added a vibration sound effect, and actual vibration of mobile devices, making it entertaining and interactive.

## Project Description 
“_It all depends on what you visualize_”. - Ansel Adams

### MoonShakers! What exactly does it do? How does it work?
Our project uses the globe.gl web component which is based on Web.gl and Three.js to make an interactive 3D globe. It creates an interactive globe on a web browser on a desktop or a mobile device. The globe can be rotated as well as zoomed in for better visualization. We have tried to depict the location and the magnitude of moonquakes through various mediums such as visual, audio, and physical representations.

#### Visual representation
##### Label  
Epicenters of moonquakes are marked by labels as mentioned in the data we have used. If you hover over the label of any moonquake you might see details about it. Details include Moonquake number, magnitude, location in lunar latitude and longitude, and date and time of moonquake. On mobile devices, labels show up on touching the labels. 
##### Ripple Radius  
We have added ripples at the epicenters of the moonquakes. The maximum ripple radius is proportional to the magnitude of moonquakes. We have used an angular radius, in radians, six times the magnitude of a moonquake. We found this value by trial and error and settled for six as it provided the best visualization for us.

##### Ripple Color  
Ripple color represents the increasing severity of moonquakes. Ripple color provides another visual representation of moonquake magnitudes. The maximum magnitude of a moonquake in our data is 3.2 as well as the minimum is 0.7. So we divided the data into four scales 0 for magnitude between 0-1, 1 for magnitude between 1-2, 2 for magnitude between 2-3, and 3 for magnitude between 3-4. The colors representing different scales of moonquakes are given below:  
- `#0066FF` blue for scale 0
- `#007800` green for scale 1
- `#FFC802` yellow for scale 2
- `#FF2A04` red for scale 3

##### Ripple Concentration  
The ripple concentration is inversely proportional to the magnitude of the moonquakes. It signifies a higher frequency for a higher magnitude of moonquakes.


##### Fading Ripples
As the shaking of a real moonquake would fade over a distance, the ripples of the moonquakes in our web app fade to zero as it reaches the maximum ripple radius defined in the sections above.

#### Audio Representation
We have used a vibration sound effect to denote the severity of moonquakes. The audio is played when clicking on the label of moonquakes on the globe. The audio is taken from freesoundeffects.com. The audio play duration is proportional to the scale (defined above) of the moonquake. The exact duration of the sound being played is 500ms×(scale+1). We added ‘1’ to the scale as our first scale is ‘0’ and if ‘1’ is not added it implies that the audio will not be played. And, we chose scale over magnitude as magnitudes give unnecessary variability of sound duration which we cannot even perceive properly. And, choosing a scale also provides consistency with the colors used.

#### Physical Representation
The physical representation of the moonquake is done by the vibration of the device. We have used the Vibration API for vibrating devices for a particular duration to represent a moonquake. The device vibrates when clicking on the label of moonquakes on the globe. Currently, Vibration API is only supported on Android devices so you may not feel the vibration when used on ios devices. (Since the label layer is below the ring layer, you might have to multiple times to touch the label on mobile devices)


