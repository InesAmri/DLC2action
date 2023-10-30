[![Generic badge](https://img.shields.io/badge/Contributions-Welcome-brightgreen.svg)](CONTRIBUTING.md)
<a href="https://github.com/psf/black"><img alt="Code style: black" src="https://img.shields.io/badge/code%20style-black-000000.svg"></a>

![](logos/title.png)

DLC2Action is an action segmentation package that makes running and tracking of machine learning experiments easy.

## Installation

### Via the Python Package Index

You can simply install DLC2Action by typing:

```
pip install "dlc2action==0.2b3"
```

### From Github

You can also install DLC2Action for development (or based on the bleeding edge) by running in your terminal:

```
git clone https://github.com/amathislab/DLC2Action
cd DLC2Action
conda create --name DLC2Action python=3.9
conda activate DLC2Action
python -m pip install .
```
### Annotation Workflow Tutorial

You can find step-by-step instructions and resources to help you navigate the annotation workflow effectively. Whether you're new to the process or seeking to refine your skills, these tutorials are designed to provide clear guidance and support. Explore the wealth of information available in our user guide and tutorials to make the most of your annotation workflow.

Check out the tutorials and user guide here [dlc2action_annotation](https://github.com/amathislab/dlc2action_annotation)

## Features

**The functionality of DLC2Action includes:**
 - Setting labels and shortcuts
 - Annotating videos
 - Saving training parameters and results
 - Running predictions and hyperparameter searches
 - Creating active learning files
 - Loading hyperparameter search results in experiments and dumping them into configuration files
 - Comparing new experiment parameters with the project history and loading pre-computed features (to save time) and previously
   created splits (to enforce consistency) when there is a match
 - Filtering and displaying training, prediction and hyperparameter search history
 - Plotting training curve comparisons
 - Filling in configuration dictionaries automatically 
 - Compiling and updating project-specific configuration files

## A quick example

You can start a new project, run an experiment, visualize it and use the trained model to make a prediction
in a few lines of code.
```python
from dlc2action.project import Project

# create a new project
project = Project('project_name', data_type='data_type', annotation_type='annotation_type',
                  data_path='path/to/data/folder', annotation_path='path/to/annotation/folder')
# set important parameters, like the set labels you want to predict
project.update_parameters(...)
# run a training episode
project.run_episode('episode_1')
# plot the results
project.plot_episodes(['episode_1'], metrics=['recall'])
# use the model trained in episode_1 to make a prediction for new data
project.run_prediction('prediction_1', episode_names=['episode_1'], data_path='path/to/new_data/folder')
```

## How to get more information?

Check out the [examples](/examples) or [read the documentation](https://amathislab.github.io/DLC2action/html_docs/dlc2action.html) for a taste of what else you can do.


## Acknowledgments

DLC2Action is developed by members of the [A. Mathis Group at EPFL](https://www.mathislab.org/). We are grateful to many people for feedback, alpha-testing, suggestions and contributions, in particular to Liza Kozlova, Andy Bonnetto, Lucas Stoffl, Margaret Lane, Marouane Jaakik, Steffen Schneider and Mackenzie Mathis.

## License:

Note that the software is provided "as is", without warranty of any kind, express or implied. If you use the code or data, please cite us!

## Reference:

Stay tuned for our first publication -- any feedback on this beta release is welcome at this time. Thanks for using DLC2Action. Please reach out if you want to collaborate!
