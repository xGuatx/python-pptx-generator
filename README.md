# Python PPTX Generator

Python scripts to automatically generate PowerPoint presentations (.pptx) with python-pptx.

## Description

Collection of test scripts to create PowerPoint presentations programmatically:
- **test.py**: Basic test script
- **test2.py**: Advanced presentation generation
- **test3.py**: Tests with structured content
- **test4.py**: Additional experiments

## Prerequisites

- Python 3.6+
- python-pptx library

## Installation

```bash
cd app

# Create a virtual environment
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install python-pptx pillow lxml
```

## Usage

```bash
# Activate the virtual environment
source app/venv/bin/activate

# Run a script
python app/test.py
python app/test2.py
python app/test3.py
python app/test4.py
```

## Features

The scripts demonstrate how to:
- Create PowerPoint presentations from Python
- Add text, titles, and content
- Structure slides with different layouts
- Generate content dynamically

## Structure

```
python-pptx-generator/
|---- app/
|   |---- test.py        # Basic test
|   |---- test2.py       # Advanced test
|   |---- test3.py       # Structured test
|   |---- test4.py       # Experimental test
|   \---- venv/          # Virtual environment (excluded from Git)
\---- README.md
```

## Important

- Generated .pptx files are **not** committed to Git (.gitignore)
- The virtual environment (venv/) is not committed
- Test/experimentation scripts - adapt according to your needs

## python-pptx Documentation

- Official documentation: https://python-pptx.readthedocs.io/
- API Reference: https://python-pptx.readthedocs.io/en/latest/api/
- Examples: https://python-pptx.readthedocs.io/en/latest/user/quickstart.html

## Usage Examples

### Create a Simple Presentation

```python
from pptx import Presentation

# Create a new presentation
prs = Presentation()

# Add a slide with title
title_slide_layout = prs.slide_layouts[0]
slide = prs.slides.add_slide(title_slide_layout)
title = slide.shapes.title
subtitle = slide.placeholders[1]

title.text = "Hello, World!"
subtitle.text = "Generated with python-pptx"

# Save
prs.save('my_presentation.pptx')
```

### Add Content with Bullet Points

```python
from pptx import Presentation

prs = Presentation()
bullet_slide_layout = prs.slide_layouts[1]
slide = prs.slides.add_slide(bullet_slide_layout)

shapes = slide.shapes
title_shape = shapes.title
body_shape = shapes.placeholders[1]

title_shape.text = 'Key Points'

tf = body_shape.text_frame
tf.text = 'First point'

p = tf.add_paragraph()
p.text = 'Second point'
p.level = 1

prs.save('presentation_bullets.pptx')
```

## License

Personal project - Private use

Test and experimentation scripts with python-pptx.
