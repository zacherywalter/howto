# python.md
everything you might need to know when running python scripts

## Environments
##### conda
[conda environment howto](https://docs.conda.io/projects/conda/en/stable/user-guide/tasks/manage-environments.html)
```bash
conda create --name <my-env>    # create new environment
conda activate <my-env>         # activate env.
conda deactivate                # deactivate current env.
conda remove --name <my-env> --all
```

## import other files into a python file.py
[source here](https://stackoverflow.com/questions/2349991/how-do-i-import-other-python-files)

### install dependencies for pip python
A Similiar thing to rdepends can be done for python-pip packages
If you want to install a bunch of dependencies from requirements.txt
to a computer with no internet connection, you would do:

```bash
mkdir dependencies
pip download -r requirements.txt -d "./dependencies"
tar cvfz dependencies.tar.gz dependencies
```
```

And, once you transfer the dependencies.tar.gz to the machine
which does not have internet you can

```
```bash
tar zxvf dependencies.tar.gz
cd dependencies
pip install * -f ./ --no-index
```
