The **TimberSeg 1.0** dataset is composed of 220 images showing wood logs in various environments and conditions in Canada. The images are densely annotated with segmentation masks for each log instance, as well as the corresponding bounding box and class label. This dataset aim towards enabling autonomous forestry forwarders, therefore it contains nearly 2500 instances of wood logs from an operators' point-of-view. Images were taken in the forest, near the roadside, in lumberyards and above timber-filled trailers. The logs were annotated considering a grasping perspective, meaning that only the logs above the piles and accessible are segmented.

## Motivation

The forestry sector has undergone significant mechanization efforts, yet there has been a notable lag in automating tasks that involve high-level cognitive functions. In contrast, industries like agriculture and mining have made substantial strides in automation over the past decade. Despite facing distinct challenges, the forestry sector is now making strides toward the integration of autonomous machines in both forest and mill operations.

Similar to the early automation of ore transportation in mining, the extraction of logs from the forest using heavy machinery is anticipated to be the initial focus for automation in forestry. Log picking, a crucial aspect of this process, poses challenges in terms of perception and manipulation. This exacerbates the persistent shortage of manpower in forestry operations, as new operators require extensive training to execute this repetitive task efficiently.

The authors' system targets the segmentation of individual logs in RGB images captured by a camera positioned in or above the operator's cabin. Detecting wood logs proves to be non-trivial due to their inherent cluttered nature. Logs, being elongated objects, are typically found scattered on the ground or in piles within recently harvested forests or lumberyards. Furthermore, logs often face partial occlusion, either from branches or other logs, complicating instance segmentation. Challenges such as variations in illumination and weather, particularly in northern countries like Canada or Sweden where forestry operations persist throughout winter in snowy conditions, further complicate the scenario.

To address these complexities, the authors have compiled a densely annotated dataset encompassing diverse scenarios, including piled and individual logs, various seasons, environments, illuminations, and perspectives.

## Dataset Collection and Labeling

The TimberSeg 1.0 dataset, is composed of 220 images containing 2500 instances of wood logs in representative environments and dispositions. These images were carefully selected to capture typical viewpoints and situations that a forwarder or wood loader operator would operate with. Images have been collected in four types of environments.

<img src="https://github.com/dataset-ninja/timber-seg/assets/120389559/d311d846-8ff8-4fa9-b248-53bb19fd410d" alt="image" width="500">

<span style="font-size: smaller; font-style: italic;">Environment Types.</span>

Forest corresponds mostly to scattered logs in freshly cut areas, whereas roadside consists of neatly piled logs ready to be transported. To compile the required data, we strategically installed three dashcams (VIOFO A129 Pro Duo 4K) on forestry forwarders operating in the vicinity of Lake Saint-Jean, Quebec, Canada. Each dashcam featured dual cameras affixed to the inner side of the cabin windows, with one camera capturing a forward view and the other capturing a sideways perspective. These dashcams meticulously recorded numerous hours of video content, spanning various resolutions (4K, 2K, 1080p) and encompassing diverse weather conditions, over several months.

Supplementing this dynamic video footage, we utilized a Canon EOS M50 digital camera to capture images in lumberyards associated with sawmills and paper mills. This included photographs taken from an elevated vantage point, offering perspectives of fully loaded timber trucks' trailers. The amalgamation of these dynamic and static images, derived from both videos and the digital camera, contributes significant diversity to the dataset.

To enhance the dataset's geographical representation, we incorporated additional images sourced from publicly available videos on the internet. This comprehensive approach ensures a rich and varied collection of data for our study. The forests images are predominant on purpose, as they exhibit harder visual conditions. The images contain a widely varying number of log instances, ranging from 1 to 29 logs, for an average of 11.3.

<img src="https://github.com/dataset-ninja/timber-seg/assets/120389559/951b80a3-3c9e-4e65-9992-77da3fcd6caf" alt="image" width="500">

<span style="font-size: smaller; font-style: italic;">Logs per image.</span>

The dataset curated by the authors underwent annotation through polygon mask segmentation facilitated by the SuperAnnotate tool. In the context of log picking, the focus was on detecting and segmenting exclusively the logs positioned atop a pile, as those not immediately accessible would become visible during the collection process. Consequently, a log was only segmented if it was within reach of the forwarder, excluding those covered by others or situated too far away.

Adopting a strategy akin to active learning methodologies, the authors leveraged their most accurate network, Mask2Former, to generate pre-annotations. This approach expedited the labeling process, allowing a human annotator to refine and correct errors introduced by the network rather than undertaking the segmentation task entirely from scratch.