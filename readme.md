# Whole Slide Image (WSI) Process

## A. Scaling
​Scaling the WSIs to specific scale and save to png format.

### **scaling/slide.py**
```
max_size = tuple(round(size * d / max(pil_img.size)) for d in pil_img.size)
```

## B. Filter
​Filtering the scaled WSIs to get tissue mask.

### **filter/basic_filter.py**
The filters of rgb channels, otsu, remove_small_holes and filter_small_objects.
### **filter/color_filter.py**
color_filter: Applying the filters to imgs.
save_display: show and save.

## C. Tile
### **tile/slide_mask.py**
Generate annotation mask and standard mask
### **tile/tile.py**
The main function is `sample_and_store_patches_svs`
tiling the WSIs to get tiles and their labels (class labels or masks) w.r.t tissue masks and annotations