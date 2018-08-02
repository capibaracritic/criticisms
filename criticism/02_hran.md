Hierarchical Recurrent Attention Networks for Structured Online Maps
================

![capibara](https://avatars2.githubusercontent.com/u/41347025?s=460&v=4)

| | Hierarchical Recurrent Attention Networks for Structured Online Maps |
|-|-|
| Authors | Namdar Homayounfar, Wei-Chiu Ma, Shrinidhi Kowshika Lakshmikanth, Raquel Urtasun |
| Published at | CVPR '18 |
| Article link | http://openaccess.thecvf.com/content_cvpr_2018/html/Homayounfar_Hierarchical_Recurrent_Attention_CVPR_2018_paper.html |
| Version read | CVF (??-07-2018) |


The illustrating results are poorly chosen: seemingly fixed y-points and without branching/joining
-------------

1. Some context

The article introduces a method for predicting lane markings on roads represented as poly-lines. The input data is a single LiDAR scan, but multiple resulting poly-lines can be combined later for different scans over time (note that exactly how is not addressed in the article). A varying number of poly-lines are supported in the method, each line is defined by a sequence of several (x,y) points.

2. The article

The article describes the method to find points in poly-lines using an RNN in section 3.3. Although figure 4 shows a 2-dimensional grid, all illustrative results show that each next y-coordinate of a poly-line is set at a fixed interval. Examples are figures 1, 7, 9, and 10: in all those figures the y-positions have a fixed distance to the previous y-position, and seem to match up nicely with all neighboring lines. Apart from this, even if the y-positions are indeed not fixed, the results show mostly trivial examples, omitting interesting cases like lines stopping early, starting late, making sudden sharp corners, branching off from each other, or joining up.

3. The criticism

It is not clear from the article whether the y-positions are fixed or not. In any case, the results shown are from very simplistic use-case, with simple lines all the way from top to bottom. More realistic use cases like branching or joining lines are not shown in the results, nor are they addressed in the article. It is unclear whether this method could at all handle joining or branching of poly-lines, given that the amount of lines predicted by the counting RNN is fixed.
