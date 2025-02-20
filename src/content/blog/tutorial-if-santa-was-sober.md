---
title: "AI Music Video Tutorial"
description: "How 'If Snata was Sober' was created"
pubDate: 'Feb 16 2025'
heroImage: '/images/blog/if-santa-was-sober/comfyui.png'
---

## How to Make an AI Music Video: A Degenerate Santa Christmas Story

Create a humorous Christmas music video about Santa being a degenerate before Christmas. Think smoking, gambling, running from the police... Namaste. 🎅💨

### Step 1: Generating the Content

#### Create the Music with Suno

- **Why Suno?** It's easy to use, and you own the music you create—perfect for personal projects. It has a great free tier but if you want to release the songs I recommend the Pro plan which you own the music even after you cancel
Here’s an affiliate link if you want to use it [Suno](https://suno.com/invite/@SamLand)
Bonus: it's cheaper than Spotify (and you own it)
- **Process:**
    1. Experiment with Suno to generate music that fits your theme and vibe.
    2. Adjust lyrics or create custom ones and feed them into Suno for a personalized touch.

![/images/blog/if-santa-was-sober/image.png](/images/blog/if-santa-was-sober/image.png)

---

#### 1.2 Generate the video with ComfyUI

- **Models Tried:**
    - Hunyaun (T2V) – my favorite for this project

**Workflow:**

1. Explore different tools to find one that matches your desired video style using the basic Hunyuan workflow example: 
    
    [https://github.com/kijai/ComfyUI-HunyuanVideoWrapper/blob/main/examples/hyvideo_t2v_example_01.json](https://github.com/kijai/ComfyUI-HunyuanVideoWrapper/blob/main/examples/hyvideo_t2v_example_01.json)
    
2. Follow the readme on the repository https://github.com/kijai/ComfyUI-HunyuanVideoWrapper
    1. At the time of this writing, it’s not on the `ComfyUI Manager` list
3. Once you’re generating, play around to find what prompts work for you. I found simpler sentences worked pretty well

![/images/blog/if-santa-was-sober/image.png](/images/blog/if-santa-was-sober/image-1.png)

#### 1.3 Generate video prompts with ChatGPT/AI

- Input your lyrics and ask ChatGPT to generate scene descriptions. Example prompt:*"Create 10 descriptions for scenes of Santa behaving like a degenerate. Use 'high quality Santa' as a prefix."*
- Refine until your outputs align with your vision.
- Tell it to use this template and to put it into a `code` block otherwise it uses it as formatting

```jsx
The user will provide lyrics and describe how they want the video to look. For each description, generate concise prompts based on the lyrics, describing one visual scene per prompt. Avoid any additional context or explanations. Ensure the response is formatted as follows and placed inside a code snippet:

```plaintext
positive:<description of the visual scene>  
negative:text, watermark  
------------
```

![/images/blog/if-santa-was-sober/image.png](/images/blog/if-santa-was-sober/image-2.png)

#### Time to Batch

1. Use lyrics as prompts for video scenes. Example: "high quality Santa smoking a cigar in a smoky room."
You’ll want to experiment to find what works best for your prompts
2. Batch generate scenes for efficiency
    - Install https://github.com/ltdrdata/ComfyUI-Inspire-Pack
    - Save prompts in `ComfyUI\custom_nodes\ComfyUI-Inspire-Pack\prompts`.
    - Store in `.txt` files for batch processing.
    
    ```jsx
    positive:high quality Santa throwing snowballs at elves, laughing loudly  
    negative:text, watermark  
    ------------
    positive:high quality Santa sneaking extra cookies from the elf kitchen  
    negative:text, watermark  
    ------------
    positive:high quality Santa pouring rum into the hot chocolate pot in the workshop  
    negative:text, watermark  
    ```

#### 1.4 (Optional) Video Upscaling

- Attempted but skipped due to time constraints. Next time, this step could further polish the visuals - I will update if I find a great option

### Step 2: Editing the Video

#### 2.1 Assemble in CapCut

- Imported all generated clips and the music track into CapCut.
- **Challenges:**
    - Limited AI features for editing.
    - Poor drag-and-drop functionality and timeline scaling.

![/images/blog/if-santa-was-sober/capcut-timeline.png](/images/blog/if-santa-was-sober/capcut-timeline.png)

#### 2.2 Trim and Clean

- Added all clips to the timeline to "bulk out" the video.
- Steps:
    1. Reduce noise and remove nonsensical clips.
    2. Resize clips if generation settings vary (try to standardize this during the generation phase to save time).
    3. Pick the best bits and cut quickly for coherence.

#### 2.3 Export

- Exported the final video for review.
- Hit a paywall for Pro features (unexpected, but sometimes necessary to save time).

![/images/blog/if-santa-was-sober/capcut-paywall.png](/images/blog/if-santa-was-sober/capcut-paywall.png)

## Final Thoughts

Making an AI music video is a creative and iterative process. Tools like Suno, ComfyUI, and ChatGPT simplify generation, but manual refinement in editing tools is still necessary. Next time, I'll explore better tools for automated editing and upscaling for a smoother workflow.