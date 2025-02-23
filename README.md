
# Morocco Food Classification Model By nouredine_kn

This project uses FastAI to create a machine learning model that classifies various types of Moroccan food based on images. The model is designed to recognize popular dishes and provide predictions with a probability score.

## Table of Contents
- [Project Overview]
- [Installation]
- [Usage]
- [Model Training]
- [Model Prediction]
- [Saving the Model]

## Project Overview
The model is trained on images of Moroccan food, leveraging the FastAI library for efficient data loading, model training, and predictions. It can classify dishes such as **Bastila**, **Couscous**, **Tagine**, and many more.

## Installation

To set up this project, ensure you have Python and the FastAI library installed. You can install FastAI using pip:

```bash
pip install fastai
```

Make sure you have the required dependencies for image processing:

```bash
pip install pillow
```

## Usage

1. **Data Preparation**: Place your food images in the `./morocco-food/` directory, organizing them in subdirectories according to their respective classes.
2. **Run the Notebook**: Open the Jupyter notebook (or your preferred Python environment) and execute the code cells to train and test the model.

### Model Training
The model is trained using a CNN (ResNet34 architecture) with a training-validation split of 80%-20%. You can fine-tune the model by adjusting the training parameters in the notebook:

```python
learn = cnn_learner(dls, resnet34, metrics=error_rate)
learn.fine_tune(1)
```

### Model Prediction
To test the model's prediction capability, provide an image path and execute the following code:

```python
img='path_to_your_image.jpg'
name,_,probs=learn.predict(img)
if max(probs).item()>0.7:
    print(f'Food type: {name}')
    print(f'Probability it\'s: {max(probs).item():.6f}')
else:
    print('Not found')
```

### Saving the Model
Once you're satisfied with the training, you can save the model for future use:

```
learn.export(r'.\morocco-food-ml-by-nouredinekn-v1.pkl')
```

# Morocco Food AI Model

## Watch the Morocco Food AI Model in Action

Video: 

<video src="https://superb-sorbet-21bb85.netlify.app/vedio.mp4" controls="controls" width="600">
    Your browser does not support the video tag.
</video>


## Contact
For questions, suggestions, or collaborations, feel free to reach out to me:

- Instagram: [nouredine_kn](https://www.instagram.com/nouredine_kn)
- Telegram: [nouredine_kn](https://t.me/nouredine_kn)

## License
This project is open-source. Feel free to use and modify it as you like.
