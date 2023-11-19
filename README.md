# BPP_PosteriorPlots
Visually pleasing figures for evaluating convergence from BPP MCMC analyses

## Dependencies
There are three R packages assumed installed
* ggplot2
* gridExtra
* stringr

## Intructions
This is a simple R script I use for evaluating convergence of MCMC analyses with BPP. Assumptions are that you have four independent MCMC analyses, such that the output from each is named `mcmc.txt` and that each exists in a folder. The folders are simply named `1`, `2`, `3`, and `4`. You could modify the script to otherwise fit your needs, but I think four runs are good enough for checking convergence.

To use the script, you want to be in the same directory that has the directories `1`, `2`, `3`, and `4` with the independent runs. Then simply go
```
R CMD BATCH plotPosteriors.R
```

or execute as you like from the R terminal.

## Output
Upon executation, four or five output figures will be created:
* ThetaPosteriors.png - A plate of all theta parameters displayed as violin plots with each distribution reprenting an independent MCMC analysis
* TauPosteriors.png - A plate of all tau parameters displayed as violin plot
s with each distribution reprenting an independent MCMC analysis
* ExtraPosteriors.png - A plate of various gene flow parameters if specified in the model. This is not generated if there are no such paramters.
* lnL.png - The log likelihood posteriors from the four runs
* NodeHeights.png - A scatterplot showing the median tau estimates from the pooled posteriors of MCMC analysis 1 and 2 versus 3 and 4. A dotted one-to-one line is provided to visually check which tau are problematic. I use this as a visual evaluation of convergence as opposed to chasing ESS values or relying on ESS alone.

## Questions
Modify as is helpful for your work. I use these mostly for internal checks and sometimes the plots make it in the supplementary material. If something does not look correct or you have suggestions or requests, send an email.


