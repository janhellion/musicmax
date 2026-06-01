# musicmax

Match Spotify CSV exports to your local music library using fuzzy matching. Generates an M3U playlist of matched tracks and exports unmatched ones for manual processing.

## Features

- Scans local music directories for `.flac`, `.mp3`, `.m4a`, `.wav`, `.ogg`
- Fuzzy-matches Spotify CSV (Artist Name(s) + Track Name) against filenames
- Artist validation — requires artist name in the file path to avoid false matches
- Generates an `.m3u` playlist of matched tracks
- Exports unmatched tracks to `_missing.csv` (ready for S2S-PRO Soulseek downloader)
- Configurable match threshold

## Usage

```
./musicmax path/to/playlist.csv /path/to/music/library
```

### Options

| Flag | Default | Description |
|------|---------|-------------|
| `-o` | `{csv_name}.m3u` | Output M3U filename |
| `-t` | `70.0` | Matching threshold (0-100) |

### Output

- `{name}.m3u` — Playlist of matched local files
- `{name}_missing.csv` — Tracks not found locally, ready for S2S-PRO

## Requirements

- Python 3.8+
- `pip install rapidfuzz`
