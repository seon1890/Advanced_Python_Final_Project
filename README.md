Contributors: Guilherme, Alex, Rakshit, Seonhye, Michael


The gpu notebook “models_gpu_colab.ipynb” is very specifically designed for Colab runtime only. This is required for the setup process of Rapids (CuML and CuDF specifically) which has been notoriously buggy outside of using this Colab setup. For this we also only took 5 million rows when reading in data since the free GPU cannot handle much more. We made a corresponding cpu script to compare apples to apples. This script takes a while to setup the rapids environment and forcibly restarts the terminal a few times, so you cannot just ‘run all’ and expect results.

The ‘models_gpu.ipynb’ in the ‘Unused Code’ folder contains supposedly working scripts for gpu enabled torch models, but it requires a very large vram that we don’t have access to

The ‘models_cpu_no_val…’ notebooks work fine off colab, but the full data one requires a lot of RAM. There is a script for evaluation in the ‘Unused Code’ folder, but we did not fully use it as it requires both a lot more time and more RAM to run properly

The “preprocessing_GPU_MODELS_ONLY.ipynb” is our test code for running and debugging the Rapids environment and is not for final evaluation purposes. 

A final note, reading and saving data may result in errors if used outside of its original runtime environment (colab for gpu, jupyter (specifically NYU OOD) for cpu) and thus may have minor directory name errors for such tasks

The dataset came from a Kaggle competition (https://www.kaggle.com/competitions/new-york-city-taxi-fare-prediction/data?select=train.csv) where we only used the train.csv dataset since the test.csv had no correct output results. The dataset is 5.7GB and its usage may be limited by your system. It is intended that the preprocessing notebook takes in and preprocesses the data first, so set/change the nrows parameter to handle the large (55M rows) dataset for your given machine/desired compute time. 5M rows seems to run well on limited devices such as free Colab with its limited RAM and GPU (if using)
