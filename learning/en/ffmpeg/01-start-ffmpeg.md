# What is `ffmpeg`

`FFmpeg` stands for **Fast Forward Moving Picture Experts Group**. It is a free and open source software project that offers many tools for video and audio processing. It's designed to run on a command line interface, and has many different libraries and programs to manipulate and handle video files.

## Install

You can download the latest `FFmpeg` builds for Windows and Linux from the official builds repository:

```url
https://github.com/BtbN/FFmpeg-Builds/releases
```

### License Choice

- **GPL versions**: Include all codecs and features - recommended for general users
- **LGPL versions**: Limited codecs - only needed if you're distributing software

### File Types

- **Static builds (without "shared")**: Single executable file, larger size, easier to use
- **Shared builds (with "-shared")**: Smaller executable but requires additional DLL/.so files in the same folder or PATH

### Verify Installation

After installation, check if `FFmpeg` is working:

```bash
ffmpeg -version
```

## Basic Concepts

### Streams

Each media file consists of multiple streams:

- **Video stream**: The moving images (abbreviated as `v` in ffmpeg)
- **Audio stream**: The sound (abbreviated as `a` in ffmpeg)
- **Subtitle stream**: Text captions (abbreviated as `s` in ffmpeg)

You can watch and saw stream information by just set input file:

```bash
ffmpeg -i input.mp4
```

And to convert a file, you simply specify input and output:

```bash
ffmpeg -i input.avi output.mp4
```

### Stream Specifier

FFmpeg uses **Stream Specifiers** to let you target specific streams. The format is:

```bash
-[option] : [stream type]
```

## Common FFmpeg Options

| Option | Description |
| -------- | ------------- |
| `-i` | input file |
| `-c:v`, `-c:a`, `-c:s` | codec |
| `-b:v`, `-b:a` | bitrate |
| `-q:v`, `-q:a` | quality |
| `-map` | stream selection |
| `-ss`, `-to`, `-t` | cut/trim |
| `-crf` | quality for MP4 |
| `-an`, `-vn` | remove audio/video |
| `-vf`, `-af` | filters |
