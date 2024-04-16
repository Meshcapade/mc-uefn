# Meshcapade Plugin for Unreal Editor for Fortnite (UEFN)

<p class='hidden'>For a better viewing experience, visit our <a href='https://me.meshcapade.com/integrations/uefn'>webpage</a>.</p>

This plugin allows you to quickly retarget motions created on the [Meshcapade.me](https://me.meshcapade.com/) platform onto your own characters in [Unreal Editor for Fortnite](https://store.epicgames.com/en-US/p/fortnite--uefn). Bodies created on the Meshcapade platform are created using the [SMPL](https://smpl.is.tue.mpg.de/) core technology, and are thus referred to as [SMPL-bodies](https://smpl.is.tue.mpg.de/license.html).

<details open>
<summary>I. Adding the plugin to your UEFN project</summary>

[Download](https://github.com/Meshcapade/mc-uefn) the UEFN directly, or grab from our [git repo](https://github.com/Meshcapade/mc-uefn).

Once you have the plugin downloaded, unzip the plugin and put the `Content` folder of your UEFN project.

![adding plugins to unreal project](images/readme_add_to_project.gif) 

<details>
<summary>II. Getting an animation from <a href='https://me.meshcapade.com' target='_blank'>Meshcapade.me</a></summary>

Currently, there are two ways to get animations from [Meshcapade.me](https://me.meshcapade.com/):
- [Motion from video](https://me.meshcapade.com/from-videos) - extract the human motion from a video.

- [Motion from text](https://me.meshcapade.com/editor) - find a human motion in our library of thousands of motions.

### A. [Motion from video](https://me.meshcapade.com/from-videos)
To get an animation from a video, visit the Meshcapade [motion from video](https://me.meshcapade.com/from-videos) page.  Follow the prompts until you've created an animated avatar.

![from video](images/readme_afv00.png)

### B. [Motion from text](https://me.meshcapade.com/editor)
To search for a motion from our motion library, visit the Meshcapade [editor](https://me.meshcapade.com/editor) page. On the top right, there is a search box where you can find animation.  Once you've found the animation you want, save the avatar into your vault.

![from text](images/readme_tmr00.png) 

</details>

<details id='downloading'>
<summary>III. Downloading the animation </summary>

Go to your [avatar vault](https://me.meshcapade.com/vault), and click the `...` on the top right corner of the avatar containing the motion you'd like to download.  In the download options, make sure that `file format` is `.FBX` (`.OBJ` has no motion) and that `Pose/Motion` is `Captured Motion`.  For `compatibility mode`, select `Unreal - no blend shapes` if you're only interested in the motion which will make the import process faster.  Choose `Unreal` if you want to use [Pose Correctives](#pose-correctives).

![download](images/readme_download00.png)

</details>

<details id='importing'>
<summary>IV. Importing the .FBX into UEFN</summary>

With the .FBX downloaded, import it into your UEFN project (File > Import).

Set the skeleton to `SK_MeshcapadeBody`.

📝 Make sure that `Import Animation` is checked.

![import00](images/readme_import00.png)

</details>

<details>
<summary>V. Retargeting the animation</summary>

One thing you may want to do is retarget the motion from the SMPL-body onto the body of your character.  To do so, you will need a retargeter.  Retargeters require two IK rigs: one for the source body, the SMPL-body in this case, and one for the target body - your character.  The Meshcapade UEFN plugin comes with a sample retargeter for the Fortnite mannequin, including an IK rig for the SMPL-body and an IK rig for the Fortnite mannequin.

### A. Creating a Retargeter

To retarget an animaiton from a SMPL-body onto a Fortnite character, the first step is to right click on it and choose `Retarget Animations`

![retargeting00](images/readme_retargeting00.png)

Uncheck `Auto Generate Retargeter`

Change the Retarget Asset to `RTG_Meshcapade_to_FN`

Double click the animation you'd like to retarget (`AS_Soccer` in this example)

Then select `Export Animations`

![retargeting01](images/readme_retargeting01.png)

For more information on this subject, see the Unreal documentation on [IK Rig Animation Retargeting](https://docs.unrealengine.com/5.3/en-US/ik-rig-animation-retargeting-in-unreal-engine/).

Choose where you would like to export it, and then click export.

You can now use this animation with any Fortnite character.  Below is an example of the soccer animation retargeted onto several Fortnite characters.

[![Retargeting Example](images/readme_preview_retargetingexample.png)](https://youtu.be/HimMaKC5-ew "Retarget Example")

</details>