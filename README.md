# Meshcapade Plugin for Unreal Editor for Fortnite (UEFN)

<!--
remove this once the page is actually live
<p class='hidden'>For a better viewing experience, visit our <a href='https://me.meshcapade.com/integrations/uefn'>webpage</a>.</p>
-->

This plugin allows you to quickly transfer the motions you create using Meshcapade technology onto Fortnite Characters in [Unreal Editor for Fortnite](https://store.epicgames.com/en-US/p/fortnite--uefn).  You can create motions on the [Meshcapade.me](https://me.meshcapade.com/) platform or using our [API](https://meshcapade.com/docs/api). Bodies created by Meshcapade are created using the [SMPL](https://smpl.is.tue.mpg.de/) core technology and are thus referred to as [SMPL-bodies](https://smpl.is.tue.mpg.de/license.html).

This plugin was developed in Fortnite 29.20 (Unreal Engine: 5.4.0).  Unreal Engine for Fortnite is currently in Beta.

<details open>
<summary>I. Adding the plugin to your UEFN project</summary>

[Download](https://github.com/Meshcapade/mc-uefn/releases/latest/download/mc-uefn.zip) the UEFN plugin directly, or grab from our [git repo](https://github.com/Meshcapade/mc-uefn).

Once you have downloaded the plugin, unzip it and put it into the `Content` folder of your UEFN project.

![adding plugins to unreal project](images/readme_add_to_project.gif) 
</details>

<details>
<summary>II. Getting an animation from <a href='https://me.meshcapade.com' target='_blank'>Meshcapade.me</a></summary>

Currently, there are two ways to get animations from [Meshcapade.me](https://me.meshcapade.com/):
- [Motion from video](https://me.meshcapade.com/from-videos) - extract the human motion from a video.

- [Motion from text](https://me.meshcapade.com/editor) - find a human motion in our library of thousands of motions.

📝 To use either of these methods, you must create an account and be logged in.

### A. [Motion from video](https://me.meshcapade.com/from-videos)
To get an animation from a video, visit the Meshcapade [motion from video](https://me.meshcapade.com/from-videos) page.  Follow the prompts until you've created an animated avatar.

![from video](images/readme_afv00.png)

### B. [Motion from text](https://me.meshcapade.com/editor)
To search for a motion from our motion library, visit the Meshcapade [editor](https://me.meshcapade.com/editor) page. On the top right, there is a search box where you can find animation.  Once you've found the animation you want, save the avatar into your vault.

![from text](images/readme_tmr00.png) 

</details>

<details id='downloading'>
<summary>III. Downloading the animation </summary>

Go to your [avatar vault](https://me.meshcapade.com/vault), and click the `...` on the top right corner of the avatar containing the motion you'd like to download, and click `download`.  In the download options, make sure that `file format` is `.FBX` (`.OBJ` has no motion) and that `Pose/Motion` is `Captured Motion`.  For `compatibility mode`, select `Unreal - no blend shapes`.

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

In UEFN, the process of transferring an animation from one character to another is called retargeting.  This plugin comes with assets for retargeting from the SMPL-body to Fortnite characters.

### A. Using the Retargeter

To retarget an animation from a SMPL-body onto a Fortnite character, right-click an animation and choose `Retarget Animations`

![retargeting00](images/readme_retargeting00.png)

To use our retargeter:
- Uncheck `Auto Generate Retargeter`
- Change the Retarget Asset to `RTG_Meshcapade_to_FN`
- Double-click the animation you'd like to retarget (`AS_Soccer` in this example)
- Then select `Export Animations`

![retargeting01](images/readme_retargeting01.png)

Choose where you would like to export it, and then click export.

You can now use this animation with any Fortnite character.  For example, the video below has the retargeted soccer animation assigned to the `Custom Idle` variable on several Fortnite `Character Device` objects.

![retargeting02](images/readme_retargeting02.png)

[![Retargeting Example](images/readme_preview_retargetingexample.png)](https://youtu.be/HimMaKC5-ew "Retarget Example")

</details>