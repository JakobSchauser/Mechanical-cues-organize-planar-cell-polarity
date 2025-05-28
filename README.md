The quantitative analysis for our paper

# Mechanical cues organize planar cell polarity during vertebrate morphogenesis and embryonic wound repair

https://www.biorxiv.org/content/10.1101/2025.05.20.654909v1
_____
Recreating the image analyses is a three-step process:
1. Using a cell-segmentation algorithm, create a mask for each cell in the image. For our analyses _cellpose_ (www.cellpose.org) was used.
2. Place the images to be qantified and their masks (named _mask_filename_) in a folder along with a _channels.txt_ that describes the channels (see example below), and use [cell-strain-from-image]/cell-strain-from-image.ipynb to detect protein aggregates, cellular bi- and tri-junction and intracell actin distributions.
3. Using the [aggregate_analysis_tools](/aggregate_analysis_tools.py), rose-plots etc. can be made (as seen in [creating_figures](creating_figures.ipynb))
___

In _channels.txt_ the ADIP-, cell wall-, and Actin-channels are defined in that order, separated by newlines, starting indexing by 0. 
(where _Actin_ is a stand-in for any non-aggregating proteins)

Example of a _channels.txt_ for an image with ADIP in the second channel and cell-wall in first channel.
```
1
0
```
Example of a _channels.txt_ for an image with ADIP in first channel, cell-wall in the second channel and Actin in the third
```
0
1
2
```

Example of a _channels.txt_ for an image only with cell-wall in the first channel.
```
-1
0
-1
```
