---
title: "Dream Popper - Hazy Memory Music Video"
description: "AI Music Video Workflow"
pubDate: 'Apr 7 2025'
heroImage: '/images/blog/dream-popper-hazy-memory/Dream-Popper-Hazy-Memory-Cover.jpg'
---

Ever tried to recall a distant memory, and it comes through in hazy fragments?

<div style="position: relative; width: 100%; padding-bottom: 56.25%; overflow: hidden;">
  <iframe 
    src="https://www.youtube.com/embed/mviSQCi_VxA?si=wRDcqJtPCkweO9Z8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen
    style="
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
    ">
  </iframe>
</div>

This music video was created using similar techniques to my <a href="/blog/tutorial-if-santa-was-sober/" target="_blank" rel="noopener noreferrer">AI music video workflow</a>, but I've advanced and started working on a more improved workflow. It still needs improvements and I think I'm just going to have to get down and dirty in the code. Workflows available <a href="#links--resources">below</a>. 

This time instead of just Text 2 Video, I focused in on using Image 2 Video to give me better control over the visuals. That way I could use Loras for specific styles. For the consistent characters I just used the same prompts for the characters. No IPAdapter or Character Lora, though I did train them, just didn't have time to get results.

To help with being able to work in bulk and because of how long the video generations took vs the image, I wanted to bulk run images, then pick my favourite outputs to then convert to video, using the same original prompt. To do this was messy using existing nodes and why I'll possibly look into making my own for how I want to work. Overall to process was:
- Figure out a theme for the song and a style (I went for watercolor to add to the romantic and hazy memory theme)
- Generate scene ideas myself and then with ChatGPT as a "Wan2.1 prompting expert"
- Convert the descriptions into JSON
- Bulk generate images, at least 4 per prompt
- Save the prompt metadata to the image
- Pick my favourite images
- Load the images and get their original prompt from the metadata
- Run I2V workflow (About 10 minutes per render at 832x480, 49frames, 16 fps, 4 seconds) * 4
- Pick my favourite video outputs
- Run the videos through ComfyUI Ultimate SD Upscaler, 2-4 frames at a time, with face detailer
  - This took about 20-30 minutes per 4 second clip. Definitely needed improving
- Put the video together in CapCut (Davinci Resolve is still dead on my computer and I can't get it going)
  - Trying to have the video work with the theme and the beats of the video

Overall this was a great project to take AI video making to the next level for myself, with still many issues left. The amount of time generating images and then videos was insane. I'm sure there's a way to improve this process and tweak the workflow to be more efficient.

Upcoming improvements for the next video is to have consistent character generation but lost a lot of time on this and wasn't getting the results I wanted and a lot of time spent on this so I'll leave that for another project. Better resource management, by getting better results. In just computing each second of the video probably took almost 2 hours of rendering and throwing stuff away, upscaling etc.

## Links & Resources
The workflows are ugly, my apologies.
- 🧑‍🎨 [**Bulk Image Workflow**](/assets/workflows/bulk-json-to-image-schnell.json)
- 🎥 [**Bulk Video Workflow**](/assets/workflows/batch-image-to-video.json)
- 📈 [**Upscale Workflow**](/assets/workflows/video-upscaler.json)
- 🎙️ [**Suno**](https://suno.com/invite/@samland) - AI Music Generation
- 👷‍♂️ [**ComfyUI**](https://github.com/comfyanonymous/ComfyUI) - Node-based AI pipeline
- 📺 [**Wan2.1**](https://github.com/Wan-Video/Wan2.1) - I2V 1.3B
- 🎨 [**Watercolor Lora**](https://civitai.com/models/734857/eldritch-watercolor-for-flux)


## Lyrics
> It was 2012 in the summer<br>
> I was seventeen and you were eighteen<br>
> You said "We're two lost souls<br>
> But we're together"<br>
> And I swear<br>
> I swear<br>
> I fell in love right there
>
> And it was the best summer of my life<br>
> You were the best thing I ever found<br>
> I was just too blind to see<br>
> That you were everything I need<br>
> And you were right there
>
> It was 2012 in the summer<br>
> I was a stoner and you were a lover<br>
> I said "We can't be friends<br>
> But I can't be your girl"<br>
> And I swear<br>
> I swear<br>
> You fell out of love right there
>
> But it was the best summer of my life<br>
> You were the best thing I ever found<br>
> I was just too blind to see<br>
> That you were everything I need<br>
> And you were right there * 6
