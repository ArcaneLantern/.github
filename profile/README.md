<h1>Arcane Lantern</h1>
<p>Arcane Lantern aims to extend Sony Alpha and FX cameras starting with the A7iv.<br />
In keeping with the tradition of Magic Lantern and Wonder Lantern, this project is named Arcane Lantern.</p>

<p>I am pleased to announce that as of 18th November 2026 <b>full frame open gate</b> for the A7iv has been proven and working in 3840x2560, tested in 24p 10-bit 4:2:2 log in X-AVC S and X-AVC HS. Details to follow in further updates.</p>

<p>I additionally have ~1.19x crop (about 30x20mm portion of the sensor) open gate working on the A7s Mark I, a camera that released in 2014. It currently records to a vertically squeezed 1920x1080 format internally to the SD card.</p>

<b>A7iv Open Gate preview</b>
<img width="2928" height="980" alt="image" src="https://github.com/user-attachments/assets/48222edb-a653-4bd3-8d88-8679bc6969dc" />
<h3>Open Gate Samples</h3>
Currently these are just boring proof of concept samples, more to follow</br >
<a href="https://drive.google.com/drive/folders/13UgRZBylJ_KSi7itRVJ3Ug6_rnbra2y4?usp=drive_link">https://drive.google.com/drive/folders/13UgRZBylJ_KSi7itRVJ3Ug6_rnbra2y4?usp=drive_link</a>


<h3>Current state of open gate for the A7iv</h3>
<ul>
  <li>It samples the entire sensor, no crop</li>
  <li>It is 3840x2560</li>
  <li><s>The LCD preview vertically squeezes (not crops) the image into the 16:9 preview window</s></li>
  <li>The preview LCD is now also patched and shows 3:2</li>
  <li><b>Desqueeze</b> mapped to C3 for normal (3:2), 1.33x anamorphic (2:1) and 1.6x anamorphic (2.4:1) lenses working</li>
  <li>Playback in camera is working - it plays back using the full LCD screen at 3:2</li>
  <li>VLC plays the file in it's correct ratio, AviDemux does not (VLC uses the real size, AviDemux uses the tag)</li>
  <li>Davinci Resolve also incorrectly verticually squeezes the footage to 16:9</li>
  <li>Currentlty this can be fixed with: <em>ffmpeg -i input.mp4 -map 0:v:0 -map 0:a? -c copy -movflags +faststart output.mp4</em></li>
</ul>

<img width="1423" height="1033" alt="image" src="https://github.com/user-attachments/assets/3ae6487c-639b-45a3-a230-56d0dcbfe14c" />
<h4>5.7K Open Gate</h4>
<b>Status:</b> in research<br />
<b>Preliminary findings:</b> 5760x3840 can be recorded and encoded to the code in 24p. Scalers still need to be checked, and a resolution/sharpness test to show an increase over regular 4K.


<h3>A7s I Open Gate</h3>
This is the Mark I, released in 2014. It currently works at 1.185x crop, for a 30x20mm sensor reading. I have not cracked full frame yet. It also vertically squeezes to 1920x1080 in the output file. I have not succeeded in 1920x1280 or higher yet. I doubt there is much interest in revisiting this.
<img width="1011" height="1280" alt="photo_2026-11-15_15-00-19" src="https://github.com/user-attachments/assets/ab4e6aa1-1f1e-44da-9441-14a867c8ba7f" />

<h3>Lens and autofocus reverse engineering</h3>
Also on the roadmap and in (slow) progress. Reasonably understood from the firmware side, some emulators built to collect data from lenses and see how they actually behave given certain signals.<br />
<b>Can you remove the 15 fps limit with non Sony lenses?</b><br />
Probably, yes. I do not have a Sony A1 or A9 series to develop on/for however.
<img width="1216" height="901" alt="photo_2026-11-12_21-31-26" src="https://github.com/user-attachments/assets/eabb2915-49f0-4c4d-958c-7d52bbcb8c2d" />


<h3>How can I help?</h3>
If you want to donate so I can put it towards an A7sIII that I can unlock open gate on that'd be swell (doubtful, but just in case, check back in a few days for details)

Willing to test firmware builds and/or write temporary ram settings to a camera?

<h3>When can I test this on my camera</h3>
I potentially may publish something I think is safe enough to distribute on Sunday night AEDST. There's a few more steps I want to solve, and throw out some more samples before doing so. In any case I will make an update by then on what I plan to do.

<h3>What about 4K 100/120 fps?</h3>
Based on available data, the sensor readout speed is likely way too low even in S35 mode. S35 *might* be able to hand 75 fps, and a 100% centre 4K crop *might* be able handle 100 fps.

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
