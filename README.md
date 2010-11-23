# What is a guide?

A guide makes it possible to read a graph, translating from the aesthetics that we perceive to the original data values. Guides are broken down into axes (guides for x and y aesthetics) and legends (guides for all other aesthetics). Axes are straightforward - just the position and the text label are needed. Legends are more complicated because they need to succinctly convey the important components of the graphic.

It's important to be able to generate guides automatically because they are essential for correct interpretation of a graphic, and they are painful to generate manually - often the code to generate a legend can be as lengthy as the code for the plot itself!

# Legends

To make an accurate legend, we need to capture:

* the name of the legend - which should default to the name of the variable
  used to generate the scaled values.

* the geom used to draw the data - the legends for a scatterplot and line plot
  should be different. 

* the range of scaled values, converted to breaks and labels. If a layer does
  not include a particular value, it should not be shown in the legend - i.e.
  if groups are distinguished by colour, and A is plotted with lines and B
  with points, the geoms used in the legend should reflect this (only applies
  for categorical values). The legend also needs to know if these values are
  numeric or text, because the default alignment will be different.

* the other aesthetics that are used on the layer: whether fixed (i.e. size
  varies but all points are red), redundant (both size and colour are mapped
  to z), separable (size and colour are mapped to a and b), or integrable (hue
  and saturation and mapped to a and b).

## Combining legends

Individual mappings are combined in two a single legend when redundant or integrable. To combine two redundant mappings the name, breaks and labels must match, and to combine two separable mappings just the name must match.
