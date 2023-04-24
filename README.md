# COMTRADE data as PRObs Observations

This repository converts data from the  UN [COMTRADE](https://comtradeplus.un.org/) database into a structure defined by the [Physical Resources Observatory (PRObs)](https://github.com/probs-lab/probs-ontology) ontology.

See [DEVELOPING.md](DEVELOPING.md) for more information about using this repository.

## Dataset structure

- Repository is a datalad dataset
- Input data files needing preprocessing are located in `raw_data/`.
- Preprocessed data files ready for conversion are located in `data/`. 
- All custom code is located in `scripts/`.
- Converted data is saved to `outputs/`.

## Installation

### Getting the code

To clone the datalad dataset, in a shell/command window (e.g. git-bash) type:

```shell
datalad clone https://github.com/probs-lab/comtrade-data.git
```
### Setting up the virtual environment and installing dependencies:

To create a virtual environment using conda/miniconda:

```shell
cd comtrade-data
conda env create
```

## Running the code

After installation

- Open a terminal / git-bash window
- Navigate to ```comtrade-data``` folder, e.g. ```cd comtrade-data```
- Activate environment using ```conda activate comtrade-data```

To download the example output data files from the server use:

```datalad get outputs```

To preprocess input data files run the script:

```doit run preprocess```

To convert the preprocessed data in the `data` folder run:

```doit run convert_data```

To run all necessary tasks (i.e. preprocessing and conversion) simply run:

```doit```

Individual files can be converted by running the `convert_data.py` script with appropriate parameters specifying the file type and the input and output filenames:

```scripts/convert_data.py comtrade data/ct-2018-imports.csv outputs/ct-2018-imports.nt.gz```

For conversion of the example COMTRADE data files the type `comtrade` should be specified.

# Converting new data

For conversion of new data files (possibly in a different format from the examples) see the [DEVELOPING.md](DEVELOPING.md) file.

## Testing the code

To test the code, after installing the software and running the `doit` script:

```cd tests
pytest
```





