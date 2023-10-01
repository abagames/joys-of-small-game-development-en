## Automatic Pixel Art Generation

Various types of tools referred to as automatic pixel art generators exist, with a common approach being to combine a multitude of predetermined parts and alter their colors to create new pixel art.[^1] This method is often employed in game avatar creation, allowing for the generation of a multitude of characters and their animations with consistency. However, this approach only allows for the creation of specific character variations. If a generator matching the desired character is not available, obtaining the desired pixel art becomes impossible.

A slightly more flexible approach involves adding dots that are randomly turned on/off to a base pixel art and through these changes, various patterns are created.[^2] With this method, by altering the base pixel art, it is possible to accommodate the generation of various characters.

I have also crafted a pixel art creation library following the method of random dot alteration.[^3] For instance, creating various shapes of spaceships using this library results in the following (click on the image to go to the demo page).

[![pixel-art-gen](https://camo.githubusercontent.com/9020e7dc180bc5c301d6ff1a65183bfa292e97c8acb154caf569b9a2b4826c2a/68747470733a2f2f61626167616d65732e6769746875622e696f2f706978656c2d6172742d67656e2f73686970732e676966)](https://abagames.github.io/pixel-art-gen/index.html?ships)

The products of this method are highly randomized, excelling at creating free-form characters like spaceships. However, they struggle with characters with constraints like monsters viewed from the side with distinct eyes, arms, and legs. Therefore, pixel art generators come with inherent strengths and weaknesses, with no one-size-fits-all solution available.

Lately, with the advent of generative AI, it has become possible to create art based on prompts, and methods to apply generative AI to pixel art have emerged.[^4] However, generative AI tends to excel at creating larger images, and is not quite suited for crafting small images like 16x16 pixel art. The evolution of technology might enable the generation of small images and their animations like pixel art in the future, but at the current moment, it has not reached a practical level yet.

---

[^1]: [pixeldudesmaker](https://0x72.itch.io/pixeldudesmaker)
[^2]: [Pixel Spaceships](http://web.archive.org/web/20080228054410/http://www.davebollinger.com/works/pixelspaceships/)
[^3]: [pixel-art-gen](https://github.com/abagames/pixel-art-gen)
[^4]: [5 Best AI Pixel Art Generators in 2023](https://mspoweruser.com/ai-pixel-art-generator/)
