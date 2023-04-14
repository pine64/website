---
title: "How \"Meet the PinePhone Pro\" was made"
date: "2021-10-27"
categories: 
  - "community"
  - "pinephone-pro"
tags: 
  - "community"
  - "pinephone-pro"
cover: 
  image: "pttitle.png"
---

![](/blog/images/pttitle.png)

As PINE64‘s flagship mainline GNU/Linux smartphone, the PinePhone Pro, was about to be announced, a trailer and some nice renderings showcasing the phone and its features had to be produced.

The groundwork for the trailer was started in February 2021 and took all the way up to a few days before the trailer was released at October 15th 2021. The work for the trailer included making the material and models, creating the scene and the surroundings, animating the scenes, establishing a story in the video, finding fitting music, cutting it and adding sound details, writing and recording the text and cutting the video, which took many hours of work until the following trailer was released:

https://www.youtube.com/watch?v=wP2-6Z74W44

The trailer is almost entirely made with free and open source software – modelling, the scenes, animations and final cut including the music is all done in Blender, vector graphics and some smaller graphical edits for the screen contents are done in Inkscape and Gimp. The trailer is made by volunteers from the community.

## The visuals

The general idea of the trailer was to tell a story: visually we wanted to lead the viewer from the history of the PinePhone, to the introduction of the PinePhone Pro including its features, to the actual usage. Not only did we want to tell the story of PINE64 making shipping such a device real but also point the viewer to what was achieved so far and what the user can achieve using the phone. We selected a darker setting for the intro part of the video and we tried to go for brighter settings mixed with realistic settings for the PinePhone Pro introduction part of the video.

For product renderings typically Blender Cycles is used, which has the downside that the raytracing can take a very long time to achieve a fine rendering quality, unlike Blender’s Eevee architecture using rasterization instead of raytracing (especially used effects such as depth of field and other makes raytracing a must here). That means even short scenes with a duration of 3 seconds (that is 60 frames per second, making such a short scene 180 individual renderings with for example 1:30 minutes rendering time per frame) took until late at night (or overnight) to finish rendering, even with the usage of CUDA and Cycles X in the Blender alpha.

![](/blog/images/pt3-1024x564.png)

Most scenes in the trailer went through multiple different versions, some of the scenes were numbered up to version 7 or 8 until we were happy with the storytelling and the visuals. Being able to build upon previously created scenes, ideas, model, textures and settings however helped with creating the finally used scenes considerably, so even after ideas were discarded the time used to create them was well-invested.

![](/blog/images/pt2-1024x564.png)

For scenes such as the privacy switches scene new techniques had to be learned to achieve visuals like floating text on top of a scene using depth of field using compositing to combine multiple scenes. All scenes also use three-point lighting. The small details make up the nice appeal of the overall trailer.

During the creative process quite a lot of scenes which were not used in the final trailer were created and some of these unused scenes were reused to create nice visuals for press images at the time of the release (see [_https://wiki.pine64.org/wiki/PinePhone\_Pro\_Press_](https://wiki.pine64.org/wiki/PinePhone_Pro_Press) for some examples) or interactive 360 degree views of the phone.

## The voice

The wonderful voice in the trailer is Bryan J. Olson, who absolutely love Linux! Pay him a visit under [https://bryanjolson.com/](https://bryanjolson.com/)

![](/blog/images/ptbryan.jpg)

_The face behind the voice: Bryan J. Olson_

## The long search for the music

Finding the best music for the trailer turned out to be difficult. We looked into various free licenses and decided that we want to prefer using CC0-licensed material if possible. At the same time we tried producing our own music inspired by some heavy piano pieces based on various examples we listened into. In the whole process we sighted material in the low three figures, including various styles such as jazz, classical music, synthwave, lo-fi and generic ambient music. As best fit turned out the song „Motions“ by Rafael Krux, licensed under CC0, after overcoming our own concerns that the music might be too cinematic.

The music had to be cut in multiple places to make it fit the story: strokes of the piano were synced with the phone or with logos and texts appearing, to seemingly integrate it into the trailer. Some subliminal sound effects were also added (such as swoosh sounds), to give movements of the phone a greater force. Cutting the music and fading parts in and out could be easily done in Blender’s video cutting interface.

![](/blog/images/pt1-1024x564.png)

We hope you enjoyed the trailer and the community work, as well as this write-up how everything was made!
