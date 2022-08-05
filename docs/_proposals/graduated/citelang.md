---
title: Tree-based software citation model
layout: proposal
tags: 
 - published
---

_Tree-based software citation model_

There is a lot of talk about software citation, but not a lot of people are working
on actual ideas for how to fix it. For this proposal we present CiteLang, the first
markdown language for citing software. Given that you have a markdown, you can
use CiteLang to easily add software citations to your markdown, AND give credit
to all the dependencies that they use. For example:

```md
## Methods

We installed @spack{name=singularity, version=3.8.2} for our analysis on @os{name=ubuntu, version=18.04},
and then thanks to @apt{name=vim, os=18.04} we were able to open a Singularity recipe in the terminal,
parse words out for machine learning, and use @pypi{name=django-river-ml, version=0.0.13} with a
custom server to run our model.
```

Then you could parse the above as text with a citation, and otherwise use CiteLang
to better understand a software dependency space.

## Graduated! 🎉️

CiteLang is graduated, and you can learn more:

 - [The CiteLang Documentation](https://vsoch.github.io/citelang) to learn about commands, background, etc.
 - [The RSEPedia Analysis](https://rseng.github.io/rsepedia-analysis/) that uses CiteLang to understand the dependency trees.
 - [CiteLang on JoSS](https://github.com/openjournals/joss-reviews/issues/4458#issuecomment-1179340245): Under review for publication in JoSS
