# InteractivePlots
Introductory scripts for using HoloViews (Bokeh backend) to generate interactive plots


## COW Tutoral and instructions for getting started can be found in the 'InteractivePlots' repository 'COW Tutorial' folder:
- Install Conda environment from InteractivePlots.yml file:
  
  ```conda env create —f InteractivePlots.yml```
- Open in a code in a notebook (requires ipython installation for VS Code or jupyter for Jupyter Lab/Notebook)

*Note: Import section of python script will require 1-2 minutes to run for first use*

**Please be aware that this package contains the tools required to prepare interactive figures and some modeling applications but may not include all necessary transformations or tests** 

## Supported HoloViews Functions (and Current Uses)
[HoloViews Reference Gallery](https://holoviews.org/reference/index.html/ "HoloViews Reference Gallery")
- hv.Scatter (bokeh backend) [HoloViews Scatter](https://holoviews.org/reference/elements/bokeh/Scatter.html/ "HoloViews Scatter")
  - 2D Models
  - Chemical Space
  - Heatmap, Bubble Plots, and Heatmap Bubble Plots
- hv.Slope (bokeh backend) [HoloViews Slope](https://holoviews.org/reference/elements/bokeh/Slope.html/ "HoloViews Slope")
  - Linear Modeling
- hv.Area (bokeh backend, plotly dependency) [Holoviews Area](https://holoviews.org/reference/elements/bokeh/Area.html/ "HoloViews Area")
  - Confidence Interval
- hv.Bars (bokeh backend) [Holoviews Bars](https://holoviews.org/reference/elements/bokeh/Bars.html/ "HoloViews Bars")
  - Data Distribution
  - Training / Validation Splits


## Possible Errors
- Hover data displays as '???'
  - JavaScript backend does not accomodate for any special characters in column names. If these are present, the column names must be changed.
- Some Bokeh color palettes cannot be found
  - If hv.extensions includes both 'bokeh' and 'matplotlib' and palette name is used by both programs (example: 'Accent'), it cannot be used. Restart notebook and remove 'matplotlib' from hv.extensions.
  - Alternatively, you can import dataframe from Bokeh directly (most cases)
    
    ```color = hv.Cycle('Category20b').values```
- Matplotlib/Yellowbrick fonts not found
  ```
  import matplotlib.font_manager
  fonts = matplotlib.font_manager.findSystemFonts(fontpaths=None, fontext='ttf')
  font_names = [matplotlib.font_manager.get_font(f).family_name for f in fonts]
  import matplotlib.pyplot as plt
  plt.rcParams["font.family"] = "DejaVu Sans"  # or another font available on your system
  ```
- VS Code not showing plot (not seen in Jupyter Notebooks)
  - Restart VS Code 
