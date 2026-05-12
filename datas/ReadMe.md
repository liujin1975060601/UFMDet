We propose UFMDet, a Unified Fourier-based Framework that formulates arbitrary-shaped object detection as continuous curve regression in a shared frequency-domain space. The key idea is to represent closed-shape and line-like objects within a single model, where line-like structures are treated as a constrained degenerate case of closed Fourier curves. As a result, UFMDet can simultaneously detect blob-like and line-like objects within a single image using a unified representation and prediction pipeline.

# Dataset Description

Four datasets (parts) are provided for download.

## 1. road_lines

A road line dataset consisting of four categories: left driving line, right driving line, left roadside line, right roadside line.

- `left`
- `right`
- `left_road`
- `right_road`

## 2. road+river_2.0

Consists of four categories: road side, river side, lake, and power line. Among them, only `ele_line` is a closed-shape (blob-like) object; the others are line-like objects.

- `road_side`
- `river_side`
- `lake`
- `ele_line`

## 3. snake.zip

Only one category: `snake`

- `snake`

## 4. remote_curves2.0

A remote sensing simulation curve object dataset consisting of four categories:

- `parabola`
- `s_curve`
- `hyperbola`
- `spiral`

---

## Data Format

The dataset is organized as follows:

/images/xxx.jpg (or .png, .bmp, .tif)
/labels/xxx.pol (corresponding to /images/xxx.jpg)
names.txt (class name list, starting from 0)
mask_line.txt (subset of line-like objects, should contain class names from names.txt)

### Label File Format: `/labels/xxx.pol`

Each line corresponds to one object (which can be either closed‑shape or line‑like).  
Each line follows the format:
cls x_0 y_0 x_1 y_1 x_2 y_2 ...... x_{n-1} y_{n-1}

- `cls` is the zero‑based class index corresponding to the class name in `names.txt`.
- If the object is a **closed‑shape** object (i.e., not listed in `mask_line.txt`), the coordinate sequence `(x_0 y_0 x_1 y_1 ... x_{n-1} y_{n-1})` represents a **closed polygon chain** that encloses the object.
- If the object is a **line‑like** object (i.e., listed in `mask_line.txt`), the coordinate sequence `(x_0 y_0 x_1 y_1 ... x_{n-1} y_{n-1})` represents an **open curve** from the start point `(x_0, y_0)` to the end point `(x_{n-1}, y_{n-1})`.
