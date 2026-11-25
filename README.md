# Brightness Is Not Information

**Can AI see what the camera never captured?** DA3021 course project by **Banoth Sree Ram Nayak** (Roll No. 240150007), IIT Guwahati, Monsoon 2026.

`index.html` is fully self-contained: every photo, figure and sound is embedded in it. Double-click it to open offline, or host it on GitHub Pages.

## What is here
- `index.html`: the whole site, self-contained (live demos run in the browser; nothing is uploaded).
- `assets/`: (for reference and reproducibility; the site does not need this folder) real photographs (CC0 / public domain, from scikit-image), experiment figures, audio and `results.json` (every number shown on the site).
- `code/`: the scripts that produced every result.

## Reproduce the results
```bash
pip install numpy scikit-image opencv-python-headless matplotlib pillow
mkdir -p models
curl -L -o models/x4plus.pth https://github.com/xinntao/Real-ESRGAN/releases/download/v0.1.0/RealESRGAN_x4plus.pth
cd code && ln -s ../models models
python experiments.py     # Real-ESRGAN experiments (about 2 min on CPU)
python experiments2.py    # Bayer, Nyquist, metamers, audio
```
`esrgan_np.py` runs the official Real-ESRGAN x4plus weights with a NumPy re-implementation of RRDBNet, so PyTorch is not required.

## Credits
Photos: Chelsea the cat (Stefan van der Walt, CC0), Coffee (Rachel Michetti, CC0), DSCOVR launch (SpaceX, public domain), Brick wall (CC0Textures, CC0), all via scikit-image.
Real-ESRGAN by Xintao Wang et al. (BSD-3-Clause). Course material: spinlabiitg.github.io/vip and /sap (N. K. Sharma).
