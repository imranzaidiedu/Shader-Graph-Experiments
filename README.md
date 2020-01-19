# Shader-Graph-Experiments

Created with Unity 2019.2.2f1
Shader Graph v6.9.1

The project contains various Shader Graph effects

## Texture dissolve 2D
<img src="https://github.com/gamedevserj/Shader-Graph-Experiments/blob/master/Images/Dissolve2D.png" height="256">

Dissolves texture using alpha clip

## Sprite outline
<img src="https://github.com/gamedevserj/Shader-Graph-Experiments/blob/master/Images/Outline2D.png" height="256">

Offsets sprite image in 4 directions to create outline

## Stealth cloak effect
### 2D and 3D
<img src="https://github.com/gamedevserj/Shader-Graph-Experiments/blob/master/Images/StealthCloak2D-WithOutline.png" height="256"> <img src="https://github.com/gamedevserj/Shader-Graph-Experiments/blob/master/Images/StealthCloak3D.png" height="256">

Uses \_CameraOpaqueTexture to imitate invisibility cloak effect
It has a couple of caveats attached to it. 

When using it with sprites, objects that should be distorted behind it need to use Shader Graph's PBR material with rendering set to opaque.

When using it with 3D models:
1. Setup your object that should become invisible to cast no shadows in the Renderer settings:
Without it there will be a shadow even if object is "invisible", because technically it's not.

2. Setup a copy of it to only cast shadows:
Shadow needs to have another material that cuts out the model allowing for light to pass through and create holes in the shadow.

3. When turning object invisible change both values in model and shadow materials 
