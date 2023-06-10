<div align="center">
  <p>
    <a align="center" href="" target="_blank">
      <img
        width="850"
        src="https://media.roboflow.com/open-source/autodistill/autodistill-banner.png?3"
      >
    </a>
  </p>
</div>

# Autodistill Base Model Template

This repository contains a templtae for use in creating a Base Model for [Autodistill](https://github.com/autodistill/autodistill).

A Base Model is a large model that you can use for automatically labeling data. Autodistill enables you to connect Base Models to a smaller Target Model. A new model is trained using the Target Model architecture and your labeled data. This model will be smaller and thus more cost effective to run.

Autodistill is an ecosystem of Base and Target Models, with the main [Autodistill](https://github.com/autodistill/autodistill) repository acting as the bridge between the two.

This repository contains a starter template from which you can create a Base Model extension.

Read the full [Autodistill documentation](https://autodistill.github.io/autodistill/).
## Steps to Build a Base Model

To build a base model, first rename the `src` directory to the name of the model you want to implement:

```
mkdir autodistill_model_name
```

Use underscores to separate words in the folder name.

Next, open the `model.py` file. This is the file where your model loading and inference code will be stored. If you need to write helper functions for use with your model -- for example, long methods for loading data, processing extensions -- you may opt to create new files to store the helper scripts.

In `model.py`, replace the `Model` class name with the name of your model.

Next, implement the following functions:

1. `__init__`: Code for loading the model.
2. `predict`: A function that takes in an image name, runs inference, and returns a `supervision` Detections object (object detection) or a `supervision` Classifications object (classification).

Update the `setup.py` file to use the name of your model where appropriate. Add all of the requisite dependencies to the `install_requires` section.

When your Autodistill extension is ready for testing, open an Issue in the main [Autodistill](https://github.com/autodistill/autodistill) repository with a link to a public GitHub repository that contains your code.

An Autodistill maintainer will review your code. If accepted, we will:

1. Add your package to the [Autodistill documentation](https://docs.autodistill.com).
2. Package your project up to PyPi and publish it as an official `autodistill` extension.
3. Announce your project on social media.