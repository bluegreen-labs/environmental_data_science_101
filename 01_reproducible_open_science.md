# Introduction

There is an increasing need to communicate transparently about science. This stems from a general climate which at times is hostile towards science, but is also rooted in the ever increasing re-use of large open datasets. The latter requirements force scientists to be more mindfull about their data practices and their scientific workflows. Aside from this broad context, reproducible science also makes science easier for all collaborators involved.

In the past, small scale analysis could rely on idiosyncratic practices from a small team of researchers. These days however datasets grow, with analysis increasing in complexity as well. This increased complexity often leads to multiple key collaborators having to work on the same project for a long time. Consequently, ad-hoc project stuctures, data naming conventions and coding practices start to form barriers for sharing work within a team or between teams (during or after publication).

# The basics: where to put things - files & folders

The easiest tools in a scientists toolset are a strong naming convention on files and folders used in a particular analysis. A consistent pattern with transparent naming can mean the difference between a collaborator hunting for a file, or knowing instantly where to look.

Storing all your data, your code and your manuscript in a singular directory might not be a wise choice. Consider this project structure. As an aside, assume that the file `manuscriptv1.docx` has been more recently updated than all other docx files.

```
phenologyleafouthypothesis/
├─ data .csv
├─ regressions.r
├─ manuscriptfinal.docx
├─ Data.csv
├─ manuscriptv1final.docx
├─ manuscriptv1.docx
├─ regression.R
```

When confronted with such a working environment a collaborator, or the original author upon returning to a project like this, will not know where to start.

We note in this instance that the naming convention of the folder is opaque, duplication data files have slightly different values (but no traceable origin), there is duplication in the statistical analysis and ambiguity on which is the true final manuscript to be considered as the data on `manuscriptv1.docx` is more recent than those flagged 'final'.

If you recognize some of these patterns in your own work, you might have encountered a loss of data (or ambiguity on its provenance), retracing a complete analysis due to inconsistencies, and lost writing efforts etc. As projects grow these kind of problems grow exponentially.

A first step to alleviate some of these issues is good naming conventions on files and folder, as well as a folder structure which mirrors function. Using these rules we can restructure this small project as such.

```
phenology_leafout_hypothesis/
├─ analysis/
│  ├─ 00_regression_analysis.R
│  ├─ 01_degree_day_model.R
├─ manuscript/
│  ├─ main_manuscript.docx
│  ├─ appendix.docx
├─ data/
   ├─ PEP725_leafout_dates_germany.csv
   ├─ README.md
```

In this case using a \_snake\_ case file naming (spaces are _ ), with descriptive names, will help with readability, while structuring folders along function increases transparency. Naming analysis files with numbered prefixes communicates the order of execution. A README document in the data folder contains meta-data on the provenance of the data.

# Structuring R projects, a template






Simple folder structures and naming conventions go a long way in making research transparent and reproducible. However, it is noted that we can't track changes in the manuscript or the code if we do not rename files (in potentially opaque ways). To further increase our reproducible science skills we'll have to use version control, in which changes to files are tracked using snapshots of this file structure.


# git integration






