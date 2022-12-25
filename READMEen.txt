░░░░░▄░░░░░░░░░░░░░░▄░░░░░░
░░░░░██░░░░░░░░░░░░██░░░░░░
░░░░░███░░░░░░░░░░███░░░░░░
░░░░░████░░░░░░░░████░░░░░░
░░░░░█████░░███░░████░░░░░░
░░░░░██████░███░██████░░░░░
░░░░░█████████████████░░░░░
▄░░▀███████████████████▀░░▄
░▀███████████████████████▀░
░▄▄████▀░▀▀█████▀▀░▀████▄▄░
░░▀▀█████▄░░███░░▄█████▀▀░░
░░░░░░▀████░███░▄███▀░░░░░░
░░░░░░░░███████████░░░░░░░░
░░░░░░░░░█████████░░░░░░░░░
░░░░░░░░░░▀█████▀░░░░░░░░░░
░░░░░░░░░░░█████░░░░░░░░░░░
░░░░░░░░░░░░▀█▀░░░░░░░░░░░░
AVAsystem
russian version in READMEru.txt

READMEen.txt
owo
This menu and functionality system for VRChat avatars allows you to quickly install a menu with support for your elements and objects on an avatar when editing it in the Unity editor and subsequently transfer it as easily as possible to new versions of the avatar bases when they are updated. Among the functions there is an analogue of the space mover, flight, flashlight, acceleration, change of clothes, change of materials (textures), dances and sounds, display of objects, spawning of objects (prefabs) in the world, resizing of the avatar, springballs, trails, free camera, teleport ( teleports only other players within the world), animation control and much more.

More clearly and in detail the installation and configuration of AVAsystem is shown in my video
AVAsystem
https://youtu.be/sLGCRG795Ho
on my channel
https://www.youtube.com/@mexafox
I did not make an English version with English voice acting due to the lack of sufficient interest of subscribers in the English versions of my videos, despite the significant laboriousness for me to create them. If you are interested in the English version, you can write about it in the comments to the video. If there is sufficient demand, I will definitely make a quality offer.

Installation: 

1. launch manually pre-installed unity editor version 2019.4.31f1 via unity hub
https://unity3d.com/unity/whats-new/2019.4.31

2. install the VRChat avatars asset, it must be included in the project
https://vrchat.com/download/sdk3-avatars

3. install the avatar base asset
https://app.gumroad.com/library
preferably Rexouium Avatar

4. install the AVAsystem.unitypackage asset

5. Optionally, you can install an avatar emulator in VRChat in order to be able to check the operation of the menu without uploading the avatar to the VRChat server each time.
https://github.com/lyuma/Av3Emulator

6. install all other desired assets into the project, for example with
https://assetstore.unity.com

7. Open the scene from its base.

8. In the AvaSystem directory, open the ava_scene.unity scene in parallel with the open scene from your base. Then drag everything related to the AVAsystem (These are all objects starting with clothes, or you can take objects from the scene) from the ava_scene.unity scene to the avatar object from the base scene and save the scene under a new name, for example mein_scene.unity, in a convenient directory . On the rest of the scenes, click discard changes and remove scene.

9. Bind the ParentConstraint from the objects headbase - Head, right_paw - Right wrist, left_paw - Left wrist to the "bones" (objects) of your avatar (when you select them, the "inspector" section opens and you need to set the Parent constraint on Sources corresponding to the name of the object "bone" from its base).

You can also make Chest_Items - ChestUp, leftleg_Items - Left toe, rightleg_Items - Right toe, hips_items - Hips, tail_items - Tail6 by analogy, but to use them you also need to enable

10. Select the first main object of your avatar base and set animation layers (animation controllers) on it: AVA_FX, AVA_additive, AVA_action. Then, in the same place, set ava_Menu as the avatar menu, and ava_Vars as the avatar parameters (if you need the operation of its menu in the basis, you will have to decide on the basis of which file to make the file with variables, depending on the amount of work to create variables, for AVAsystem, use 17 variables, but only 4 variables of the integer type are required)

11. Open the ava_menu/actions.asset file and put a menu from your base on rex as a Sub Menu. Well, rex can be renamed to the name of your base.

12. Set the optimal position of the viewpoint for your avatar View Position in the VRC Avatar Descriptor (I have X=0, Y=1.78, Z=0.2, the display in this case is displayed normally, without additional settings and the view on the avatar body is similar to the view in the real world).

13. You need to adjust the distance from the eyes to the display. This is done by changing the Position parameter on the Z axis from the display object, which lies in the headbase.
It is also desirable to change the name of the texture and display material so that it does not conflict with other avatars that also have AVAsystem. To do this, go directly to the Unity editor into the ava_materials directory and rename the display22.mat and display22.renderTexture files there to arbitrary names. After renaming, it is desirable to make sure that the texture with the already new name is still set to the material, and the material with the new name is still set to the display.

14. If desired, throw clothes on your base by dragging the bones of its armature into the bones from the base by their respective names. And throw the visual part of the clothes into, for example, into clothes top_clothes top1. Another surface of clothing to replace the first, respectively, in top2, etc. Accordingly, in bottom_clothes and other_clothes, by analogy, throw off the surface of the clothes, which should turn on simultaneously with the pen.

15. If you wish, throw prefabs of any of your items (objects) into the numbered objects of spawners and numbered objects "attached" to the limbs of the avatar. When setting them, you will have to turn on older objects in the hierarchy, and after setting up new objects, do not forget to turn them off (do as it was). When adding new objects, do not forget to unpack the prefabs and reset the coordinates (or create a new object).

16. To cast a sound, you need to select the desired object in sound / Audio1, etc. and in the audio clip set the audio file

17. To install the dance, you need 2 files: an audio file and an animation file. Audio files, like sounds, are installed into music objects, such as music1. And to install the dance animation, you need to open the AVA_action.controller file in unity (the extension is not displayed in unity, just select it in the list of files in unity), and then go to the Animator tab. This animation controller will be opened there, you need to go to the "Action" layer, select the appropriate dance (Dance1, dance2) and in motion select your dance animation.

18. To test the menu directly in unity, you need to run the emulator. To do this, after creating the scene, open the "tools" menu and select "Enable Avatars 3.0 emulator". Then press start project and select the avatar object. A menu will appear in the inspector section. There is also a detailed emulation of the VRChat menu.

19. Upload an avatar in VRChat to your account, using the Unity section of the "VRChat SDK" menu item "Show Control Panel", go to your account there and upload an avatar.

20. Enjoy new opportunities to explore worlds and don't ever cheat in co-op games with other players, don't be bad :). Everywhere play honestly, respectfully to other players, according to the rules accepted by all, so that other players, against the background of the majority, also do not want to break the rules and create cringe. Miow, OwO.

Note
The system in its original form is resource-intensive, by default it includes everything that can be useful for exploring worlds and having fun. Therefore, after testing the functions you need, I recommend removing everything unnecessary from it, from variables to layers of animation controllers and unnecessary files, so as not to overload the devices of other players.


Usage in VRChat menu:
first button
off all
disables all selected objects on the avatar.

items
menu for managing items, clothes, and avatar skin, spawners, springballs and the painting system. In the submenu with clothes, in addition to choosing clothes, there is a change in materials (textures) of both clothes and an avatar.

fly
flight mode. Takeoff requires the avatar to be off the ground (terrain collader). The flight goes with the forward movement keys in the direction of view. To accelerate and quickly take off, you can press the jump (if it is allowed).

flash light
flashlight

actions
everything related to actions is located here: acceleration, sound control menu and starting dances, movement menu (starting animations of sitting, lying, etc.), the original menu from the avatar, the camera in simple mode and advanced, full screen display and chroma key, advanced mode with camera turns, teleport activation, camera point selection, breathing, switching to female version, avatar resizing, tail movement, right paw lift, collider wall, trails, particles, tongue and muzzle

space_mover
after turning it on with the button, you can move the avatar in space along 2 axes (vertically and back and forth, which gives a third-person view). To reset the viewpoint and switch it to the eyes of the avatar, you need to press view_move (only works vertically).


free packages used in the project:
UNITY TECHNOLOGIES
Unity Particle Pack

MOONFLOWER CARNIVORE
Particle Attractor

JMY Studio
Electronic Music For Video Games Free

KEVIN IGLESIAS
Dance Animations FREE

TimeOfDay&WeatherSystem

free resources from discord:
https://discord.gg/rexouria

and many more sources (for example, animations copied from various freely distributed assets), which I unfortunately did not write down in a timely manner, because I wanted to view more assets and learn more methods in order to complete the project faster

Therefore, the project is free and free in terms of distribution and modification, please do not delete the authors from this file and do not forget to add yourself at the end with a list of your changes, so that users know their saviors and benefactors,

Mexafox (Alex Miller)
more than 180 hours spent on work
Added:
control menu, animation controllers action, additive, FX, variables (vars.txt file, which lists all variables with their descriptions, ava_vars.asset file with variables from AVAsystem and rexouium), flight mode, bright flashlight, accelerator, analogue of Space mover ( Locomotion) on 2 axes, animations of standing, lying, dancing, sound, switching materials, switching objects on the limbs and torso of the avatar, collider scoop, drawing system, springballs with object selection, camera system with full screen mode and chroma key, camera positioning points, advanced camera positioning mode, binding stations configured for teleport to the camera (you can teleport other players to a point in front of the camera), trails (tails behind the character), avatar scaling, tail movements, turning off breathing for the rexouium avatar, fixing the hood muscles, switching to the female version of rexouium , right forepaw raise, item spawner in front of avatars, two separate object spawners with reference to the world ( the object selected through the menu is fixed in the world and remains in place, even if the avatar itself moves in the world), a "collider wall" flying forward with a fireball (strongly pushes objects on the map that the avatar itself can push), the choice of particle effects (particle).