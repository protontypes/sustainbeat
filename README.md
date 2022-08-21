# AwesomeCure
>  Analyze and cure awesome lists by mining, processing and plotting data from listed Git projects.

AwesomeCure provides basic scripts to analyze Git projects within an Awesome list getting an overview of the represented open source domain. Use the GitHub API to retrieve project meta data and generate various metrics about the state of the project. As a result, a CSV is created to sort and analyze the listed projects according to the different criteria. 

## Background

"Awesome List" are a central part of the open source ecosystem. They allow developers to get an overview of open source projects in different domains. A cross-platform search engine for open source projects does not yet exist. Therefore, they represent the central index for the diverse open source communities, so that development resources are concentrated and the wheel is reinvented again and again.

Maintaining an Awesome list requires removing inactive projects on a regular basis, investigating new projects and engaging the community to update the list. Without these measures, new and still active projects get lost in the multitude of inactive projects. The processing of such list additionally gives the possibility to analyze these ecosystems with the help of data science methods in order to identify potentials and risks within the domain. 

## Application Example
The [OpenSustain.tech](https://opensustain.tech/) website is based on such an Awesome list, giving an overview of the active open source projects in climate and sustainable technology in general. 

Most of the entries are linked to GitHub or GitLab repository of the underlying project. Therefore, AwesomeCure is able to analyze every project via the platform API to extract meta data from the listed projects. In this way, various health indicators are extracted for every active and listed project within the ecosystem like:

* Last activity
* Community Distribution Score ( How much does the project depend on a single person)
* Number of reviews per pull request
* Days until the last commit and last closed issue
* Total number of stars, contributors
* Use licenses 
* Any many more...

The method can be applied to other open source areas as well. Since all official Awesome lists are checked with a linter to the standard "awesome" format, the tool is able been develop to be compatible with most awesome lists. 

## Install

Clone the GitHub repository:

```
git clone git@github.com:protontypes/AwesomeCure.git
```

Then, install Jupiter notebook:

```
pip install jupyterlab
pip install notebook
```

Then, add a `.env` with your personal GitHub token to the root project folder (see more information on that [here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token).  An API key does not need any special permissions. This file is excluded version by the .gitignore file and in this way not uploaded to GitHub. 

```
jupyter notebook
```
A browser window should open, if not, click (or copy paste) the link from your terminal output.

## Architecture

The project was split into two Jupyter notebooks.  One for data acquisition and one for data processing and plotting. 

### Data Acquisition

The [AwesomeCure](./awesomecure.ipynb) notebook lets you read the Awesome List from any repository. Depending on the size of the list the processing can take multiple hours.

![AwesomeCure](./docs/AwesomeCure.png)

### Data Processing

Data processing is done in the [ost_analysis.ipynb](ost_analysis.ipynb) with the output csv files form the data acquisition. Since not API key is needed for this step the processing can also been done online within Binder:

 [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/protontypes/AwesomeCure.git/HEAD)

![OST_Analysis](./docs/OST_Analysis.png)

## Results
Plotting the dataset gives insides into the Open Source Ecosystems from different perspectives. 

### Programming Languages 

![programming_languages](./docs/programming_languages.png)

### Project Scores 

![Score_example_plot](./docs/Score_example_plot.png)


### Communities and Organizations 

![organizations](./docs/organizations.png)

![organizations_forms](./docs/organizations_forms.png)
