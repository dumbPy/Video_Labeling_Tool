# vVidLabeler
A Video Labeling Tool for labeling Whole Videos, Video Frames and adding multiple tags to each frame.


### Steps for Labeling:
* Select Video root folder (it will find all videos in subfolders)
* Select Label Folder (labels and config will be saved in this folder)
* Press `OK`
* For each frame, you can add and remove tags by toggling keyboard chars
* Selected `tags` (in the list menu on left) are registered with `frameLabels` when you press `arrow_keys` or `space` exclusively used for `frameLabels`
* `classLabel` for the whole video can be registered with on right. new `classButtons` can be added with the `New Class` *lineEdit* provided.
* click `next Video` button to save the registered *frameTags*, *frameLabels* and *classLabel* to a json file with the same video name in `labelFolderPath` selected at the start with *select Folder Dialog*
  

### Labels Format
```
{"frameLabels":[["Up", ["P", "R"]],
               [["Left", ["P", "R"]]
                .
                .
                .

                ],
 "classLabel" :"SomeClass",
 "config"     :{}
}
```
where:
* `["P", "R"]` is the sorted list of Tags for the 1st and 2nd *frame*
* `"Up"` is the frameLabel for 1st *frame* registered by pressing Up_Arrow
* `"someClass"` is the classLabel for whole video, registered by pressing push buttons on the right, and new classes can be added on the fly
* `"config"` is currently of no use and can be used to save more fine information of the frames in future
  
### Screens
![First Screen](images/screen1.png)

![Annotation Window](images/screen2.png)


### Bugs
* Crashes with `segmentation fault` in windows on selecting the paths and doesn't display even a single frame
* Randomly crashes in Linux with same `segmentation fault` but resumes at the same video without any loss of data for the previously labeled videos as they are already exported to json, and the `<labelFolderPath>/config/config.json` tracks the index, so restarting gets the last shown video, not having to go through already labeled videos.