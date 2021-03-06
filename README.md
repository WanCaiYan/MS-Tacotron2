# MS-Tacotron2
Tacotron2 based multi-speaker text to speech 

## Reference

 - Deep voice 2
 - [NVIDIA tacotron 2 implementation](https://github.com/NVIDIA/tacotron2)
 
## Model
Three places adding speaker embedding layers
 - text encoder GRU initial state
 - add speaker code after text encoder RNN

## Data preparation
```data```:dictionaries for different language  
```dataset```:where put training data and test data

## Train step
```
python -m multiproc.py train.py -o outdir15/ -l logdir -c ./outdir5/tacotron2_statedict.pt --warm_start
```

## Experiments
### E1 (Jan-19)
**location**: 115 **outdir14**
**data**: 
- mix indirect and direct speech with one speaker code + 39 female speaker from cusent   
- storytelling sentences share the same speaker id 

### E2 (Jan-24)
**location**: 114 **outdir15**
**data**: 
- mix indirect and direct speech with one speaker code + 39 female speaker from cusent   
- indirect speech: spk id 69 direct speech: spk id 70

## Install
- apex segmentation error: ```conda install -c psi4 gcc-5```
## TO DO LIST
- tweak input format : replace with pandas dataframe instead of filelists