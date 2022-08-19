<p align="center">
  <img width="100" src="https://raw.githubusercontent.com/llbit/chunky-docs/master/images/logo.png" alt="Chunky logo">
</p>
<h1 align="center"> Chunky Gallery </h1>

<div align="center">Chunky is a Minecraft rendering tool that uses Path Tracing to create realistic images of your Minecraft worlds. View the website <a href="https://chunky-dev.github.io/docs/" target="_blank">here</a>. This is the repository for the <a href="https://chunky-dev.github.io/gallery/" target="_blank">Chunky Gallery</a>.</div>

## Build Instructions

This site uses <a href="https://www.mkdocs.org/" target="_blank">mkdocs</a>. Python version 3.5 or greater is required.

1. Clone this repository.

2. (optional) Set up a Python <a href="https://docs.python.org/3/library/venv.html" target="_blank">virtual environment</a>.

3. Install the required packages with pip by using the command, `pip3 install -r requirements.txt`.

4. If running Windows, simply run `serve.bat`. Otherwise, change the working directory to `./ChunkyGallery`.

5. Serve the site for development by using the command, `python -m mkdocs serve --dev-addr 127.0.0.1:8001`.

6. Build a preview of the final site by using the command, `python -m mkdocs build`.

---

## Usage of `auto_gallery.py`

- `gallery.csv` -  Contains a list of all Gallery entries we have. Due to mistakes that I have made we currently only have "full" information for only new submissions.
- `templates\` - Contains some .html templates which are used to create original image pages and gallery containers.
- `ChunkyGallery\gallery\index.md` - is the target file for the script and must have `<!--GALLERY_START-->` and `<!--GALLERY_END-->` tags in order for the script to function.

### New Entries
1. Import new entries from `https://docs.google.com/spreadsheets/d/1B3PD0AAc_gwNES8b1uaETQwswkjEcHbwJy8EH9M1k88/edit?usp=sharing` into `gallery.csv`
2. Clean-up new entries in `gallery.csv`; add missing credits, clean up features, etc.
3. Run `auto_gallery.py`.
4. Fix any errors you come across... This is usually stray spaces
5. PR `images\gallery\` changes first
6. PR all other changes

### For updating templates/force re-gen

By default we do not re-generate files.

1. Delete/clear `ChunkyGallery\gallery\img\thumbnail` and `ChunkyGallery\gallery\image_html` | It is not recommended to clear `images\gallery`. As some entries do not have a Google Drive URL we cannot recover these easily.
2. Run `auto_gallery.py`.
3. Fix any errors you come across....
4. PR as normal
