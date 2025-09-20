# Cartography & Basemaps
*How can we transform raw spatial data into maps that are intuitive, beautiful and genuinely useful?*

When people think about data science, they often jump straight to algorithms and models. However, even the most cutting-edge model is near useless if people can’t interpret its results. That’s where good design comes in, and as a Geographer with a particular interest in spatial data, I’ve developed a strong appreciation for cartographic design.

<br>

This is a small but meaninful project I undertook as part of my work for the Cartography & Data Visualisation module in my final year at UCL. It was formative in crystallising my appreciation of how careful design decisions (like a consideration of visual hierarchy, colour theory and the role of basemaps for spatial data) make all the difference when it comes to work being uninterpretable and overlooked versus intuitive and able to drive decision making. 
Though the data itself is extremely simple in this case, the process helped developed a strong foundation that I'll be able to apply to more analytically complex projects in the future. 

<br>

I chose to map Port Moresby, Papua New Guinea for this exercise - a rarely represented city, and somewhere with interesting surrounding terrain which provides a strong showcase for the potential of thoughtful basemap design. 
<br>

---


### Data Sources:

**Topography**: Terrain raster from [OpenTopography.com](https://portal.opentopography.org/datasets) <br>
**Roads, Waterways, Administrative Extent & POIs**: Shapefiles from [Natural Earth](https://www.naturalearthdata.com/)
<br>


### Methodology:

The basemap was created by blending two topographic layers - both versions of the same raster downloaded from [OpenTopography.com](https://portal.opentopography.org/datasets):

  1. **Bidirectional Hillshade Layer**: Provided the texture of the surrounding *Owen Stanley Mountain Range*
     - Deep rainforest green colour selected for shadows - sampled directly from a photo of the PNG rainforest itself *(see below)*
  2. **Elevation layer**: From a copy of the same raster layer and rainforest photo, I devised a colour palette to represent land and sea elevations - toning down colours slightly to ensure the basemap remained subtle enough.

<p align='center'>
  <img src=assets/img/colour%20palette%20inspo.png alt="Palette Inspo" width="400" />
  <img src=assets/img/basemap%20layers.png alt="Topographic Layers" width="500" />  
</p>

By layering and blending these, the basemap successfully evokes the local environment, whilst being subtle enough to allow the road and water networks to retain the map's overall purpose.
<br>


### Additional Design Decisions:
  - Roads: mapped using neutral browns, hirearchy demarcated using line thickness and opacity
  - Water: slight transparency reduction so topography reads clearly beneath
  - City extent and core: subtle white and grey tones to demarcate administrative boundary & make it more intuitive
These decisions produced a visual hierarchy so intuitive that a legend is not required to interpret the map.
<br>

### The Result:

Here is the final map - though the data in this case is very simple, this exercise highlights the subtle decisions that can take maps visualisations from plain to compelling; a vital step in making any Data Science project truly impactful.

![Final Map](Port%20Moresby.png)
