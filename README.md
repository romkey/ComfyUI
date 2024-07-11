# ComfyUI - Thanks to Keith Hanson for the main work!

## Quick Start

1. Update your NVIDIA Drivers (only NVIDIA cards supported right now)
2. Install Docker and NVIDIA's container toolkit (Windows: Install WSL, then install Docker Desktop)
3. Run the following command if all you want is a ComfyUI: 
4. Have roughly 20GB of space ready for default models and room to grow for any others you might want to add!

```
docker run --name comfyui -p 8188:8188 --gpus all -it --rm -v comfy:/storage fcogomez/comfy-ui:latest
```

### Run it as a service

```
docker run -d --name comfyui --restart=unless-stopped -p 8188:8188 --gpus all -it -v comfy:/storage fcogomez/comfy-ui:latest
```

## Features

### Prepackaged Custom Nodes

Popular custom nodes:

- https://github.com/ltdrdata/ComfyUI-Inspire-Pack.git
- https://github.com/ltdrdata/ComfyUI-Impact-Pack.git 
- https://github.com/cubiq/ComfyUI_IPAdapter_plus.git 
- https://github.com/storyicon/comfyui_segment_anything.git 
- https://github.com/Gourieff/comfyui-reactor-node.git  
- https://github.com/WASasquatch/was-node-suite-comfyui.git 
- https://github.com/pythongosssss/ComfyUI-Custom-Scripts.git
- https://github.com/RockOfFire/ComfyUI_Comfyroll_CustomNodes.git
- https://github.com/Kosinkadink/ComfyUI-Advanced-ControlNet
- https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite
- https://github.com/Fannovel16/comfyui_controlnet_aux
- https://github.com/jags111/efficiency-nodes-comfyui
- https://github.com/Kosinkadink/ComfyUI-AnimateDiff-Evolved.git
- https://github.com/Fannovel16/ComfyUI-Frame-Interpolation.git

### Automatic downloading of models at boot

We place a sample "extra_downloads.yml" file in your storage directory. 

Edit that file to download and place any custom models you'd like to have, then restart the container and watch the magic.

See this file for our default models we download at boot: [extra_downloads.yml](extra_downloads.yml)

To add your own models, take note that the `path` item in the yml is the path inside the container. 

All paths should generally use `/storage/ComfyUI/.../...` unless you have very good reason not to.

Once the file is placed for the first time in your storage directory, it won't be overwritten again.

### Requirements:

1. Windows or Linux Operating System (Mac unsupported for now)
2. NVIDIA GPU of series 2xxx or better (ideally)
3. Updated CUDA drivers (update your graphics drivers)
4. Docker installed and working with NVIDIA container support (Use WSL and Docker Desktop for Windows!)
5. 50-100GB+ of HDD space (roughly 10GB for the default models and 8GB for the container alone
