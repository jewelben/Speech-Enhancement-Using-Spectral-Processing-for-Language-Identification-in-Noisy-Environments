This file is the README for spectral processing and LID

# Spectral Processsing

The Speech enhancement codes can be found in the file `speech_enhancement.ipynb`. The file `speech_enhancement.ipynb` contains the following functions:

### addWhiteNoise(data, SNRdB)

This function adds white noise to the input data. The SNR is specified in dB.

### addNoise(data, SNRdB, noise_type)

This function adds noise to the input data. The SNR is specified in dB. The noise type can be specified as `pink`, `white`, `babble`, `factory1`, `factory2` etc as per the available noise files in the `noises\noises` folder.

### spectralSubtraction(x, frame_length, order)

Performs spectral subtraction on the input data. The frame length and order of the processing are specified as parameters.

### mmse(x, frame_length)

Performs MMSE on the input data. The frame length is specified as a parameter.

### showSpectrogram(x, nFFT, title)

This function plots the spectrogram of the input data. The number of FFT points and the title of the plot are specified as parameters.

# LID

The LID codes can be found in the file `gmm_lid.ipynb`. The file `gmm_lid.ipynb` contains the following functions:

### training(train_data_path,feat_train_path,trained_model_path, n_mix, max_it, n_mfcc, inc_mfcc,inc_mfccd, inc_zfcc, inc_mfccdd, feat_red_method)

This function trains the GMM model. The training data path, feature path, trained model path, number of mixtures, maximum iterations, number of MFCCs, `inc_{}` which is used to use that particular feature for training,and feature reduction method ("none", "pca", "trunc_svd") are specified as parameters.

### testing(test_data_path,feat_test,trained_model_path, n_mfcc, inc_mfcc, inc_mfccd, inc_mfccdd, inc_zfcc, feat_red, apply_feat_red)

This function tests the GMM model. The test data path, feature path, trained model path, number of MFCCs, `inc_{}` which is used to use that particular feature for testing, feature reduction method ("none", "pca", "trunc_svd") and whether to apply feature reduction (`True` if "pca" or "trunc_svd" are used) or not are specified as parameters.

It should be noted that the LID code is written to be ran on Google Colab. The paths are set accordingly. If you are running the code on your local machine, you will have to change the paths accordingly. Testing and Training Data can be specified accordly with proper annotations. For example, if you choose to test noisy data against an LID trained on a clean model, paths must be specified accordingly.

# Noise Addition

The noise addition codes can be found in the file `noise_addition.ipynb`. The file `noise_addition.ipynb` contains the following functions:

### addNoise(data, SNRdB, noise_type)

This function adds noise to the entire dataset. The SNR is specified in dB. The noise type can be specified as `pink`, `white`, `babble`, `factory1`, `factory2` etc as per the available noise files in the `noises\noises` folder. Note that this **WILL OVERWRITE** the original dataset with noisy data.

# Dataset Enhancement

The dataset enhancement codes can be found in the file `dataset_enhancement.ipynb`. Enhancemnt is done using MMSE estimator.



