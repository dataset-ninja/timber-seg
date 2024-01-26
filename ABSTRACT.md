The **TimberSeg 1.0** dataset is composed of 220 images showing wood logs in various environments and conditions in Canada. The images are densely annotated with segmentation masks for each log instance, as well as the corresponding bounding box and class label. This dataset aim towards enabling autonomous forestry forwarders, therefore it contains nearly 2500 instances of wood logs from an operators' point-of-view. Images were taken in the forest, near the roadside, in lumberyards and above timber-filled trailers. The logs were annotated considering a grasping perspective, meaning that only the logs above the piles and accessible are segmented.

## Motivation

Forestry has seen a large mechanization effort, yet little
has been done on automating tasks requiring high-level cognition. In the last decade, other industries such as agriculture
and mining, made significant progress towards automation.
While facing different challenges, forestry is catching up towards autonomous machines in the forest and mills.
Just like the ferrying of ores has been one of the first tasks
automated in mining , it is presumed that forwarding
operations, i.e., extracting logs from the forest with heavy
machinery, will be the first candidate for automation.
Log picking is an essential component in this forwarding
task, but is challenging from a perception and manipulation perspective. This exacerbates the ongoing manpower
shortage in forestry operations, as novice operators require
lengthy training to accomplish this repetitive task. The authors system aims at segmenting
individual logs in RGB images from a camera placed in
or above the operator’s cabin. One reason that detection of wood logs is non-trivial is that they
tend to be cluttered by nature. Indeed, logs are elongated
objects that are generally found either randomly spread on
the ground, or in piles throughout the recently harvested
forest or the lumberyard. Moreover, they suffer from partial
occlusion, either from branches or simply other logs, which
makes instance segmentation more challenging. Variations
in illumination and weather in outdoor locations are also
challenging, especially in northern countries such as Canada
or Sweden. In these areas, forestry operations are performed
throughout the winter, thus in snowy conditions.