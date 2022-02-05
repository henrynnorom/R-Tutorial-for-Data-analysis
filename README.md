# R-Tutorial-for-Data-analysis #Tutorial for Data Analysis using R
# The aim of this tutorial is to help you get started using the R environment for scientific data analysis.
The workflow for data analysis: Import; Check; Describe; Transform; Analyse the Data and Store important results such as graphics or tables as files.

# You may find a list of available data sets by typing data() at the console.
# We use the data set PlantGrowth. To get basic info

?PlantGrowth
PlantGrowth
snip

# Summary information via summary (PlantGrowth)
summary(PlantGrowth)

# To get summary information for each level of the group variable, 
# for each treatment) use
by(PlantGrowth, PlantGrowth$group, summary)

# to get a boxplot of weight separately by group, use the comman boxplot
?boxplot
boxplot(weight~group, data = PlantGrowth)

# The plot still lacks some labels, which we add (together with some color for the boxes)
boxplot(weight ~ group, data=PlantGrowth, main="Plant Growth
data", ylab="Dried plant weight", col="cyan")

# perform an analysis of variance use lm(), Our model is pg.lm:
pg.lm <- lm(weight ~ group, data=PlantGrowth)
pg.lm

# To get a bit more information, use summary(pg.lm)
summary(pg.lm)

# To test the signifcance of the group difference,
anova(pg.lm)

# using the plot command #demonstrate methods of plot() function
plot(PlantGrowth)
plot(pg.lm)


#clean up
rm(pg.lm)
