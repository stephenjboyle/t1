# Converting new data

To add a new file {filename}.csv for conversion, copy the file to the `data` folder, create a file {filename}\_defs.dlog containing appropriate meta-data (specifying the prefixes to use in the converted RDF data) and modify `dodo.py` as appropriate.
 
If the data format is different to that of the examples, a new file load\_data\_{type}.rdfox will need to be created to specify the mapping between the columns of the input csv file and the columns of the RDFOX tuple table used to store input data. A file map_{type}.dlog will also need to be created to specify conversion rules. These files should be copied to the ```scripts``` folder.

To convert the data run `doit run convert_data`.

The results will be in the `outputs/` folder.

To test the expected values are present, run `pytest`.
