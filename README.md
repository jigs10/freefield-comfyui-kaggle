# ComfyUI + FreeField on Kaggle

A simple Kaggle notebook that sets up [ComfyUI](https://github.com/comfyanonymous/ComfyUI) with the [FreeField](https://github.com/neuregex/ComfyUI-freefield) custom node and gives you a public link to the UI using Cloudflare Tunnel.

## What it does

- Installs ComfyUI
- Stores models in `/tmp` so `/kaggle/working` doesn't fill up
- Installs the FreeField node
- Starts ComfyUI with `--lowvram`
- Exposes the UI through a `trycloudflare.com` link

## How to use

1. Upload `comfyui_freefield_kaggle.ipynb` to Kaggle (File > Import Notebook).
2. In the notebook settings, turn **Internet ON** and pick your accelerator.
3. In the **Set HF Token** cell, paste your Hugging Face token.
4. Run the cells from top to bottom.
5. Open the `https://...trycloudflare.com` link printed by the tunnel cell. Keep that cell running.
6. When you're done, run the last cell to stop everything.

## Notes

- Models live in `/tmp/models/`, so they are deleted when the session ends. You need to download them again next time.
- The public link changes every run.
- No GPU? Add `--cpu` to the start command in the **Start ComfyUI** cell.
- Never share your notebook with your real HF token inside it.

## Credits

- [ComfyUI](https://github.com/comfyanonymous/ComfyUI) by comfyanonymous
- [ComfyUI-freefield](https://github.com/neuregex/ComfyUI-freefield) by neuregex
- [Cloudflared](https://github.com/cloudflare/cloudflared) by Cloudflare
