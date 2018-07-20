Multi-task Self-Supervised Visual Learning
================

![capibara](https://avatars2.githubusercontent.com/u/41347025?s=460&v=4)

| | Multi-task Self-Supervised Visual Learning |
|-|-|
| Authors | Carl Doersch, Andrew Zisserman |
| Published at | ICCV '17 |
| Article link | https://arxiv.org/abs/1708.07860 |
| Version read | v1 (25-08-2017) |


Section 3.3 on harmonizing network inputs: the inputs aren't harmonized
-------------

1. Some context

When training a multi-task network conflicts could occur depending on the tasks, e.g. a 3-channel color image cannot be fed in if one of the tasks is grayscale-to-RGB colorization. The article acknowledges this and addresses it by "harmonizing network inputs". This is listed as one of its contributions and discussed in section 3.3.

2. The article

One of the arguments the authors make is that when the network input is not harmonized (e.g. fed in either one grayscale or three color channels): "(...) it gives the network an opportunity to cheat: the network might recognize which task it must solve, and only represent information which is relevant to that task, instead of truly multi-task features". Indeed, this could be the case. However, this issue is 'solved' in the article by only harmonizing across 2 of the 4 tasks considered: "Hence, to harmonize, we replace relative position's preprocessing with the same preprocessing used for colorization".

3. The criticism

On itself the harmonization contribution is already a bit weak, but it doesn't seem to be actually addressed (only across 2 of the 4 tasks), and the network can still 'cheat' to some degree. A more elaborate analysis of this issue would be interesting to see, including a full-harmonization and its impact on the accuracy of the various tasks.


Section 6 on the accuracy results: other experiments could have been more insightful
-------------

1. Some context

In the article a network is pre-trained on four 'self-supervised' tasks, after which it is fine-tuned and evaluated on three other tasks (ImageNet, PASCAL VOC, NYU depth). This seems to be the main storyline of the article: the four self-supervised tasks are not considered the final goal, but the three tasks are. Results are reported e.g. in figure 3 and figure 4.

2. The article

To show the generality of the learned features, most of the learned parameters in pre-training are frozen when fine-tuning, only the last few layers/blocks are trained on the final datasets. This however results in accuracy numbers that are overall significantly worse compared to training the exact same network from scratch on the target dataset. One exception is the NYU depth task, for which results are roughly on-par.

3. The criticism

Although the experiments are useful and valid, a proper experiment to evaluate the practical use seems to be missing: now that we have a pre-trained network with generic features, can we do well with much less labeled data? Of course, for these tasks labeled data is available, but for others it might not yet be or might be expensive to annotate. Such a pre-trained network with generic features can then be very useful. An experiment of this form can easily be conducted: e.g. repeat the ImageNet experiment (figure 4 top), but now assume the dataset is only labeled for 50%, or 20%, or even 5%. In such cases the benefit of this article might be shown clearly, as it could very well beat a network trained from scratch on such a small dataset.

