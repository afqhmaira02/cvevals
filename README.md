# Roboflow Evaluations 🔎

[Roboflow Evaluations](https://github.com/roboflow/evaluations) is a framework for evaluating the results of computer vision models. Think [OpenAI Evals](https://github.com/openai/evals), but for computer vision models.

Roboflow `evaluations` is a Python package for evaluating computer vision models.

Using evaluations, you can:

1. Compare ground truth to a Roboflow model to benchmark and visualize model performance on images in bulk;
2. Test different Grounding DINO prompts to see which one most effectively annotates a specified class in an image;
3. Test different CLIP prompts to see which one most effectively classifies an image, and;
4. Evaluate resuts of different confidence levels for active learning.

Performance is measured using an aggregate of the following metrics:

- **Precision**
- **Recall**
- **F1 Score**

Evaluations works with YOLOv5 PyTorch TXT data for object detection and Multiclass Classification TXT for classification.

Only Roboflow models are supported to retrieve ground truth, but any model can be evaluated. Support for other model types is coming soon.

If the device on which an evaluation is run has a CUDA GPU, that GPU will be used for running model inference for Grounding DINO and CLIP. Otherwise, inference is run via CPU.

Here is an example confusion matrix from inference on a single image using Grounding DINO:

![Confusion Matrix](example.png)

## Getting Started

To get started, clone the repository and install the package:

```
git clone https://github.com/roboflow/evaluation

pip install -e .
```

See the files in the `examples` directory for demos showing how to start using Roboflow Evaluations with:

1. CLIP classification;
2. Grounding DINO, and;
3. A Roboflow model.

For instance, to run an evaluation of a Roboflow model, open up the `examples/roboflow_example.py` file, replace your workspace ID, model ID, and version number, then execute the script to run an evaluation.

The script will print the following pieces of information to the console:

- An aggregate confusion matrix showing performance of the model on the dataset
- The precision, accuracy, and f1 score of the model performance

To use GroundingDINO, run the `dinosetup.sh` script in the root `evaluations` directory. Then, you can use the corresponding `DINOEvaluator` object as documented in the project docs.

## License

This project is licensed under an [MIT License](LICENSE).

## Contributing

Interested in contributing to evaluations? Check out our [contributing guidelines](CONTRIBUTING.md).

## TODOs

- Show an example aggregate confusion matrix in the README