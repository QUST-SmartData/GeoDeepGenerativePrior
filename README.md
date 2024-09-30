# GeoDeepGenerativePrior

This is the official repository for "[Prior-Guide Adaptive Gan Method for Various Borehole Image Inpainting](https://doi.org/10.1190/geo2023-0418.1)". Please cite this work if you find this repository useful for your project.


During geophysical exploration, inpainting defective logging images caused by mismatches between logging tools and borehole sizes can affect fracture and hole extraction, petrographic analysis and stratigraphic studies. However, existing methods do not describe stratigraphic continuity enough. Also, they ignore the completeness of characterization in terms of fractures, gravel structures, and fine-grained textures in the logging images. To address these issues, we propose a deep learning method for inpainting stratigraphic features. Firstly, to enhance the continuity of image inpainting, we build a generative adversarial network (GAN) and train it on numerous natural images to extract relevant features that guide the recovery of continuity characteristics. Secondly, to ensure complete structural and textural features are present in geological formations, we introduce a feature-extraction-fusion module with a co-occurrence mechanism consisting of channel attention(CA) and self-attention(SA). CA improves texture effects by adaptively adjusting control parameters based on highly correlated prior features from electrical logging images. SA captures long-range contextual associations across pre-inpainted gaps to improve completeness in fractures and gravels structure representation. The proposed method has been tested on various borehole images demonstrating its reliability and robustness.

## Usage

### Requirements

* python>=3.6
* pytorch>=1.0.1
* others

    ```sh
    pip install -r requirements.txt
    ```

### Get Started

Before start, please download the pretrained BigGAN at [Google drive](https://drive.google.com/drive/folders/1buQ2BtbnUhkh4PEPXOgdPuVo2iRK7gvI?usp=sharing) or [Baidu cloud](https://pan.baidu.com/s/10GKkWt7kSClvhnEGQU4ckA) (password: uqtw), and put them to `pretrained` folder.

Example1: run image colorization example:
    
    sh experiments/examples/run_colorization.sh   

The results will be saved in `experiments/examples/images` and `experiments/examples/image_sheet`.

Example2: process images with an image list:
    
    sh experiments/examples/run_inpainting_list.sh   

Example3: evaluate on 1k ImageNet validation images via distributed training based on [slurm](https://slurm.schedmd.com/):

    # need to specifiy the root path of imagenet validate set in --root_dir
    sh experiments/imagenet1k_128/colorization/train_slurm.sh   




