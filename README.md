# image_compression

Minimal Windows console utility that converts an image to JPEG and reduces JPEG quality until the encoded output is at or below a requested target size when that target is achievable.

## Current status

This is a small source-level prototype, not a packaged production application. The implementation currently uses .NET's `System.Drawing` JPEG encoder and expects a Windows environment with the required runtime support.

## Usage

Run the program and either provide an input image path as the first argument or enter it when prompted. Then enter the desired maximum size in KB and the output path.

Example:

```text
image_compression.exe "C:\\images\\photo.png"
Enter the desired file size in KB: 500
Enter the output file path: C:\\images\\photo-compressed.jpg
```

The tool starts at high JPEG quality and progressively lowers quality until the encoded image fits the requested limit or the quality range is exhausted. The source image is not modified.

## Limitations

- Output is always JPEG, regardless of the source format.
- A requested size is a target maximum, not a guarantee: some images cannot be reduced below the requested size using the current encoder and quality range.
- The prototype currently has no packaged installer or GUI.
- JPEG metadata, transparency, and other source-format-specific features may not survive conversion.

## Updating

`main` is the source of truth. Use the documented manual update procedure in [UPDATE.md](UPDATE.md). Automatic self-updating is intentionally not enabled while the project remains an un-packaged source-level prototype.

## License

No explicit license has been declared yet; treat the repository as source-available rather than assuming reuse rights.
