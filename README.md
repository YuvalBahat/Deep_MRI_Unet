# [Deep learning for undersampled MRI reconstruction](https://arxiv.org/pdf/1709.02576.pdf)
![alt text](https://github.com/hpkim0512/Unet/blob/master/web/img/architecture.png)

# Prerequisites
- Python
- [Tensorflow-gpu](https://anaconda.org/anaconda/tensorflow-gpu)
- [h5py](www.h5py.org/)
- [imageio](https://anaconda.org/conda-forge/imageio)

# Usage
To train a model with dataset Version 7.3 MAT-file 'data_set.mat' ([Download](https://drive.google.com/file/d/19Q3XUzfKqIquNxCFGAM2uiKzADt_8gH_/view?usp=sharing)):

    ... add MAT-file to data directory  => ./data/data_set.mat ...
    $ python main.py --ckpt_dir=<path_to_new_model_dir> --data_set=<path_2_training .mat file> --logs_step=100

'dataset.mat' have to consists of 'input' and 'label' whose shape as [width, height, num_of_data].

![alt text](https://github.com/hpkim0512/Unet/blob/master/web/img/matfile_format.JPG)

If you have more than one GPU, it supports to activate multi-GPUs:

    $ python main.py --data_set=data_set --num_gpu=4

On the other hand, you can download a trained model at [here](https://drive.google.com/file/d/1FR71iw9Ia_6kMXcoDvbGJv_kmRQhdHlj/view?usp=sharing]).

To test with an existing model (./logs/model) and test_set Version 7.3 MAT-file 'test_set.mat' ([Download](https://drive.google.com/file/d/1y6NcCqALeyN3zgIxqyJAlYDDTHYy3qzi/view?usp=sharing)):

    ... add MAT-file to data directory  => ./data/test_set.mat ...
    $ python main.py --is_train=False --ckpt_dir=<path_to_model_dir> --test_set=<path_2_test .mat file>

# Folder structure
    ├── main.py
    ├── data (not included in this repo)
    |   ├── data_set.mat
    |   └── test_set.mat
    ├── model.py
    ├── ops.py
    ├── utils.py
    └── logs (not included in this repo)
        └── model
    
