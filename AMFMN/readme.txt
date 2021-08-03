Installation

We recommended the following dependencies:
Python 3
PyTorch > 0.3
Numpy
h5py
nltk
yaml



file structure:
-- checkpoint    # savepath of ckpt and logs

-- data          # soorted anns of four datesets
    -- rsicd_precomp
        -- train_caps.txt     # train anns
        -- train_filename.txt # corresponding imgs
        -- test_caps.txt      # test anns
        -- test_filename.txt  # corresponding imgs
        -- images             # rsicd images here
    -- rsitmd_precomp
        ...
    -- sydney_precomp
        ...
    -- ucm_precomp
        ...

-- exec         # .sh file

-- layers        # models define

-- logs          # tensorboard save file

-- option        # different config for different datasets and models

-- Rct           # calc Lct, which is not published this time

-- util          # some script for data processing

-- vocab         # vocabs for different datasets

-- seq2vec       # some files about seq2vec
    -- bi_skip.npz
    -- bi_skip.npz.pkl
    -- btable.npy
    -- dictionary.txt
    -- uni_skip.npz
    -- uni_skip.npz.pkl
    -- utable.npy

-- data.py       # load data
-- engine.py     # details about train and val
-- test.py       # test k-fold answers
-- test_single.py    # test one model
-- train.py      # main file
-- utils.py      # some tools
-- vocab.py      # generate vocab

Note:
1. In order to facilitate reproduction, we have provided processed annotations.
2. We prepare some used file in []  passwd:


Run: (We take the dataset RSITMD as an example)
Step1:
    Put the images of different datasets in ./data/{dataset}_precomp/images/

    --data
        --rsitmd_precomp
        -- train_caps.txt     # train anns
        -- train_filename.txt # corresponding imgs
        -- test_caps.txt      # test anns
        -- test_filename.txt  # corresponding imgs
        -- images             # images here
            --img1.jpg
            --img2.jpg
            ...

Step2:
    Modify the corresponding yaml in ./options.

    Regard RSITMD_AMFMN.yaml as opt, which you need to change is:
        opt['dataset']['data_path']  # change to precomp path
        opt['dataset']['image_path']  # change to image path
        opt['model']['seq2vec']['dir_st'] # some files about seq2vec

Step3:
    Bash the ./sh in ./exec.
    Note the GPU define in specific .sh file.

    cd exec
    bash run_amfmn_rsitmd.sh

Note: We use k-fold verity to do a fair compare. Other details please see the code itself.



