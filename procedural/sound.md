## Automated Generation of Background Music and Sound Effects

What kind of background music (BGM) suits a small game? One type of BGM that comes to mind is that found in old arcade games. By 'old,' I am referring to games such as Xevious or Dig Dug from the early 1980s. Retro arcade games of this era often featured BGM composed of short phrases, about 4 to 8 measures in length, which were repeated.

There are several technologies available for automatically generating such BGM. One of them is WolframTones.[^1] This seems convenient. However, it appears to have a limitation: it cannot reproduce common phrases seen in old games, like a bass line oscillating in perfect fifths at sixteenth notes.

Among the latest technologies, there's OpenAI's Jukebox;[^2] however, it generates musical waveforms rather than notations, making it unsuitable for retro games. A similar technology, MusicLM,[^3] has an 8-bit sample available, and seems capable of creating chiptune-like tracks, though it still feels overly rich in expression.

This brings us to Magenta,[^4] a research project by Google, applying machine learning to music and art. Magenta.js [^5] has been released as an implementation that runs in a browser.

Magenta.js, when provided with a music score, utilizes MusicRNN [^6] to automatically generate a subsequent phrase. If given a short score from a retro game, it can produce another piece with a similar vibe. I created a simple demo program to test this out (click the image to go to the demo page).[^7]

<a href="https://abagames.github.io/short-vgm-generator/build/"><img src="https://raw.githubusercontent.com/abagames/short-vgm-generator/main/docs/screenshot.png" alt="Short VGM generator" width="700"/></a>

Upon clicking the 'Generate' button in the center of the screen, a new phrase based on the phrase on the left is generated and displayed, played on the right. It generates a simple phrase consisting only of melody and bass tracks, but it's able to produce a tune reasonably reminiscent of retro game music. For multiple tracks, each phrase is created separately, and adjustments are made in case the bass is discordant with the melody (ensuring the frequency ratios are about 1 to 4). Unchecking the checkbox below the center disables this adjustment, allowing for more freeform phrase generation.

When it comes to the automatic generation of sound effects, it seems to be difficult with MusicRNN, which targets melodies. Instead, there are numerous waveform-based solutions, many based on sfxr.[^8] These tools can be utilized to add simple sound effects to action games.

---

[^1]: [WolframTones](https://tones.wolfram.com/about/how-it-works)
[^2]: [Jukebox](https://openai.com/blog/jukebox/)
[^3]: [MusicLM: Generating Music From Text](https://google-research.github.io/seanet/musiclm/examples/)
[^4]: [Magenta](https://magenta.tensorflow.org/)
[^5]: [Magenta.js](https://hello-magenta.glitch.me/)
[^6]: [MusicRNN](https://magenta.github.io/magenta-js/music/classes/_music_rnn_model_.musicrnn.html)
[^7]: [short-VGM-generator](https://github.com/abagames/short-vgm-generator)
[^8]: [sfxr](http://www.drpetter.se/project_sfxr.html)
