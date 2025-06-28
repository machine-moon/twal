# twal

`twal` is a simple Python CLI tool for managing and switching wallpapers on GNOME desktops. It lets you browse, randomize, and save/restore your favorite wallpapers, organized by category.

## 48 Themes & 685 Unique Wallpapers -- From: [HyDE](https://github.com/HyDE-Project/hyde-gallery).

This collection features **48 curated themes** and **685 unique wallpapers**. I personally cleaned and organized the data to make browsing and switching wallpapers effortless.
You can download the full, ready-to-use set from one of the following links (use either if one isn't working):

- [MEGA.nz download](https://mega.nz/file/Ww53HYRa#2kVseOCFmunQWE9t5WhNnvxTvkAm1VbEbfPzntZAu_c)
- [Transfer.it download](https://transfer.it/t/ylesjppREZ6K)

## Installation

1. **Download the images**  
    Download and extract the wallpapers from the links above to a folder, e.g. `~/wallpapers`.

2. **Set the wallpaper directory**  
    Open `twal` in a text editor and set the `BASE_DIR` variable at the top to the path where you extracted the wallpapers:
    ```python
    BASE_DIR = "/home/youruser/wallpapers"
    ```

3. **Make the script executable**  
    ```sh
    chmod +x /path/to/twal
    ```

4. **Add `twal` to your PATH**  
    - Move or symlink the script to a directory in your PATH, e.g.:
      ```sh
      cp /path/to/twal ~/.local/bin/
      ```
    - Or add the script's directory to your PATH in your `.bashrc` or `.zshrc`:
      ```sh
      export PATH="$PATH:/path/to/twal-executable"
      ```
    - Reload your shell or source your profile:
      ```sh
      source ~/.bashrc
      ```

## Usage

```
./twal <x> <y>       : Set wallpaper at category <x> and index <y>
./twal next          : Switch to the next wallpaper
./twal prev          : Switch to the previous wallpaper
./twal random        : Set a random wallpaper
./twal status        : Display the current wallpaper and category
./twal save <alias>  : Save current wallpaper state as <alias>
./twal load <alias>  : Load wallpaper state from <alias>
```

### Examples

- `twal 2 5` — Set the 5th wallpaper in the 2nd category
- `twal random` — Choose a random wallpaper
- `twal status` — Show the current wallpaper and category
- `twal save work` — Save the current wallpaper state as "work"
- `twal load work` — Restore the "work" wallpaper state

## How It Works

- **Wallpaper folders**: Each category is a subfolder in your `BASE_DIR`, with wallpapers inside a `wallpapers/` subdirectory.
- **.twal_state**: Stores the current category and wallpaper index so you can resume where you left off.
- **.twal_aliases**: Lets you save and load named wallpaper states for quick switching.

## Requirements

- Python 3
- GNOME desktop (uses `gsettings` to set wallpapers)
- Only tested on Fedora 42, but should work on other GNOME-based distros
- Make sure your wallpaper directory structure matches the expected format

## License

This project is licensed under the terms of the GNU General Public License v3.0.  
See the [LICENSE](./LICENSE) file for details.  

