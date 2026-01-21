<img width="1734" height="673" alt="image" src="https://github.com/user-attachments/assets/01b72f39-01cb-4691-8d57-de93a36f1bc5" />


#### using intel scenescape for digital twin solution
- capture camera feeds and contextualise with computervision (object detection - bounding boxes)
- inference with region of interest, tripwires
- draw data from IMB (intel message bus) to make data-driven decisions

#### lessons learnt
- can run on 2d plane or 3d twins but will disrupt the camera calibration and might need to reconnect the camera streams to the scene
- camera calibration intuitive but must be done with reference point captured in both camera feeds and uploaded scene
- executed using docker containers and the deployment yaml file utilises all the generic ports (443, 8000). might disrupt if running other workloads occupying the common ports
- the application are pre-configured to run on igpu/dgpu. More than capable to run on CPU but need to remove the build instructions in the yaml file

```
devices:
      - "/dev/dri:/dev/dri"
```

#### Additional
The out-of-box experience can be downloaded directly from Scenescape's [git repo](https://github.com/open-edge-platform/scenescape). 
I have provided an additional 3D file for the queuing scene provided in the default Scenescape. 
