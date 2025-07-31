# HLM

The HLM is the method for using the language models to convert a helical filament into vectors. These filament vectors can be used for further processing. 
![alt text](https://github.com/smallelephant9516/HLM/blob/master/HLM.png)

## Dependencies:

python3

pytorch >= 1.7

numpy

umap-learn

scikit-learn

gemmi (for reading modern RELION star files)

### HLM-BERT
TO use the HLM-Bert, an additional hugging face environment needs to be installed from here: https://huggingface.co/docs/transformers/installation

## RELION Version Support

HLM now supports multiple RELION versions and CryoSPARC:

- **RELION 3.0** (datatype=1): Legacy RELION 3.0 star file format
- **RELION 3.1** (datatype=0): RELION 3.1 star file format with optics groups
- **RELION 5.0** (datatype=3): Modern RELION 5.0 star file format with enhanced features
- **CryoSPARC** (datatype=2): CryoSPARC particle data format

## Usage

running the jupyter note embedding.ipynb to get the embedding vector of each filament and separate them into different clusters using HLM_word2vec method, also, try to run HLM bert method, you can run the jupyter notebook BERT.ipynb

Or run:

     $ python HLM.py --o your_output_directory --in_parts your_star_file --datatype 3

For RELION 5.0 star files, use `--datatype 3`. Use `-h` to check all possible commands and options.

### Examples:

For RELION 5.0:
```bash
python HLM.py -i particles.star --o output_dir --datatype 3 --model word2vec
```

For RELION 3.1:
```bash
python HLM.py -i particles.star --o output_dir --datatype 0 --model word2vec
```

For CryoSPARC:
```bash
python HLM.py -i particles.cs --o output_dir --datatype 2 --model word2vec
```
