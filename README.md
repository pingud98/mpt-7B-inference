# MPT 7B inference code using CPU

Run inference on the latest MPT-7B model using your CPU and just 8gb of ram. If you have more ram (32gb), then you should check out the [original repo](https://github.com/abacaj/mpt-30B-inference) which has a much larger LLM.  This inference code uses a [ggml](https://github.com/ggerganov/ggml) quantized model. To run the model we'll use a library called [ctransformers](https://github.com/marella/ctransformers) that has bindings to ggml in python.

Turn style with history on latest commit:

![Inference Chat](https://user-images.githubusercontent.com/7272343/248859199-28a82f3d-ee54-44e4-b22d-ca348ac667e3.png)

Video of initial demo:

[Inference Demo](https://github.com/abacaj/mpt-30B-inference/assets/7272343/486fc9b1-8216-43cc-93c3-781677235502)

## Requirements

I recommend you use docker for this model, it will make everything easier for you. Minimum specs system with 8GB of ram. Recommend to use `python 3.10`.

## Tested working on

AMD Ryzen 3750h with 16GB RAM, running Ubuntu 22.04 LTS. Runs fine, if not the fastest. 

## Setup

First create a venv.

```sh
python -m venv env && source env/bin/activate
```

Next install dependencies.

```sh
pip install -r requirements.txt
```

Next download the quantized model weights (about 4GB).

```sh
python download_model.py
```

Ready to rock, run inference.

```sh
python inference.py
```

Next modify inference script prompt and generation parameters.
