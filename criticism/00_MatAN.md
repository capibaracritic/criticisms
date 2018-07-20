Matching Adversarial Networks
================

![capibara](https://avatars2.githubusercontent.com/u/41347025?s=460&v=4)

|  | Matching Adversarial Networks |
|-|-|
| Authors | Gellert Mattyus, Raquel Urtasun |
| Published at | CVPR '18 |
| Article link | http://openaccess.thecvf.com/content_cvpr_2018/CameraReady/2427.pdf |
| Version read | Camera Ready (07-2018) |


Section 4.2 on results for CityScapes: the comparisons are very biased
-------------

1. Some context

The article introduces a network architecture for semantic segmentation using a generator and a discriminator network, as is also used in other cGAN approaches. They compare on among others the CityScapes dataset.

2. The article

The visual comparison in figure 4 is against the Pix2Pix cGAN method, in which it shows that the presented work is visually better. Although it is perhaps useful to include another cGAN method in the comparison, Pix2Pix is far from the state-of-the-art for CityScapes. Furthermore, the comparison is with a result solving a different problem: Pix2Pix is trained with an additional background class (see e.g. the black part at the bottom of the image in figure 4 in the Pix2Pix column), but the article's method isn't. Another visual comparison, in figure 5, is against some artificial constructed case with perturbed inputs and a CE loss. Furthermore, the quantitative comparison in table 1 is against a simple cross-entropy use-case, not against the state-of-the-art. Note that the bold numbers are not the highest values in the table.

3. The criticism

The article introduces some new method to solve semantic segmentation, but it is actually far from the state-of-the-art. On itself that could still be valuable, but that should be stated clearly in the article. Currently the experimental section is constructed in such a way that it seems like new steps have been taken forwards for CityScapes, but the method actually under-performs when compare to a simple cross-entropy loss.
