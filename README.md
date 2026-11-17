# S.T.A.L.K.E.R. HUB slides

This public repository supplies the launcher's rotating background images.
The launcher checks `launcher-slides.json` on startup and when its **ATUALIZAR**
button is used. It downloads changed images from `slides/` and verifies each
file with SHA-256 before adding it to the local cache.

## Adding an image

1. Copy a `.png`, `.jpg`, `.jpeg`, or `.bmp` file into `slides/`.
2. Add its filename and SHA-256 to `launcher-slides.json`.
3. Commit and push both files. Players receive the new image the next time the
   launcher checks this repository.

Get the hash in PowerShell with:

```powershell
Get-FileHash .\slides\your-image.png -Algorithm SHA256
```

The manifest format is:

```json
{
  "version": 1,
  "images": [
    {
      "file": "your-image.png",
      "sha256": "64 hexadecimal SHA-256 characters"
    }
  ]
}
```
