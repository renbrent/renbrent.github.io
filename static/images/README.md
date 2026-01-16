# Placeholder Images

Add your portfolio images to this directory:

- `profile.jpg` - Your profile photo (recommended: 400x400px, optimized WebP/JPG)
- `favicon.ico` - Site favicon (32x32px)
- `projects/` - Project screenshots and images

## Image Optimization Guidelines

Following constitution performance requirements:

- **Format**: WebP with JPG fallback
- **Max size**: 200KB per image
- **Compression**: Use tools like ImageOptim, Squoosh, or TinyPNG
- **Dimensions**: 
  - Profile: 400x400px
  - Project screenshots: 1200x630px (maintains aspect ratio)
  - Hero images: 1920x1080px max

## Tools for Optimization

- [Squoosh](https://squoosh.app/) - Online image optimizer
- [ImageOptim](https://imageoptim.com/) - Mac app for compression
- [TinyPNG](https://tinypng.com/) - PNG/JPG compression

Place your optimized images here and reference them in `hugo.toml` using paths like `/images/profile.jpg`.
