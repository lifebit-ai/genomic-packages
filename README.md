# genomic-packages
Centralised repo for genomics analyses related R packages 


## Instructions to populate the repo

The repo will become a centralised resource for evaluating R packages related to GWAS. The repo folder structure we are complying to is the following:

```
.
├── README.md
├── assets
│   └── ...
├── gwas
│   └── {gh_user}-{gh_repo}
│       ├── README.md
│       └── notebooks
│           ├── custom
│           │   └── {name-of-custom-R-notebook}.ipynb
│           └── vignettes
│               └── {exact-name-of-vignette-from-repo}.ipynb
└── prs
│   └── {gh_user}-{gh_repo}
│       ├── README.md
│       └── notebooks
│           ├── custom
│           │   └── {name-of-custom-R-notebook}.ipynb
│           └── vignettes
│               └── {exact-name-of-vignette-from-repo}.ipynb
.
.
.
```

## Adding folders in this repo

We have curated a list of R packages related to genomic analyses, for example GWAS. The curated resource for GWAS can be found as a .csv file in [assets/gwas-packages.csv](https://github.com/lifebit-ai/genomic-packages/blob/main/assets/gwas-packages.csv). 

To add a new folder with a new tool:

### 1. select a tool from this csv that matches the following 2 criteria:

a. Is in active development in the current year, eg. 2020
b. Is relevant to Human genetics

### 2. Create a branch following the naming convention:

**adds**-**{gh_user}-{gh_repo}**

For example for the package hosted in https://github.com/dongjunchung/GGPA/, the name of the branch should be:

`adds-dongjunchung-GGPA`.

### 3. Create your changes

Add a folder inside the :warning: `gwas` :warning: named after the github user and the repo name: **{gh_user}-{gh_repo}** 

For example for the package hosted in https://github.com/dongjunchung/GGPA/, the name of the folder should be:

`dongjunchung-GGPA`.

Inside the folder add the following files:

```
├── gwas
│   └── {gh_user}-{gh_repo}
│       ├── README.md
│       └── notebooks
│           └── vignettes
│               └── {exact-name-of-vignette-from-repo}.ipynb
```

#### A. Contents of the `gwas/{gh_user}-{gh_repo}/README.md` file

The `gwas/{gh_user}-{gh_repo}/README.md` should have the following markdown content:

```log
#  [`{gh_user}`/`{gh_repo}`](https://github.com/`{gh_user}`/`{gh_repo}`)

> Description from assets/gwas-packages.csv for given R package
```

For example for the package hosted at:

```log
#  [hclimente/martini](https://github.com/hclimente/martini/)

> 🍸Systems-biology approach to GWAS, now in R!
```


#### B. Contents of the `gwas/{gh_user}-{gh_repo}/notebooks/vignettes/` folder 

The `gwas/{gh_user}-{gh_repo}/notebooks/vignettes/` should include the Rmd vignettes from the respective R package but converted to .ipynb format.

**FAQ**:

- "Where do I find vignettes?"

Most R packages have a folder named `vignettes`, for example see here:
https://github.com/hclimente/martini/tree/master/vignettes

All the files that have `.Rmd` suffixes are the package vignettes. We want to have these files inside this centralised repo.


- "How do I convert Rmd files to ipynb?"

Before moving vignettes in this repo, we need to convert them to ipynb notebooks, to be able to view them in a JupyterLab session.
For this purpose we can use a tool named `jupytext`. To install `jupytext` in an environment with conda available type the following:

```
conda install jupytext -y
```

To use `jupytext` to convert an Rmd file to an ipynb notebook:

```
wget https://raw.githubusercontent.com/hclimente/martini/master/vignettes/scones_usage.Rmd
jupytext --to ipynb scones_usage.Rmd
```


You will see the following message:

```
[jupytext] Reading scones_usage.Rmd
[jupytext] Writing scones_usage.ipynb
```

The ipynb R notebook has been successfully created and is ready to be commited in the relevant folder eg.:

`gwas/hclimente-martini/notebooks/vignettes/scones_usage.ipynb`


For vignettes, do not edit the name, use the auto-generated file from Jupytext.
