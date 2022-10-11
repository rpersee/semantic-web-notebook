# semantic-web-notebook
semantic-web-notebook is a Jupyter Docker Stack image for Semantic Web.
It includes the [Jupyter-RDFify](https://github.com/SemWebNotebooks/Jupyter-RDFify) IPython plugin developed by the [Chair of Information Systems at RWTH Aachen University](https://dbis.rwth-aachen.de/).

# Usage

Start a Jupyter Server instance with:
```
$ docker run -it --rm -p 8888:8888 -v "${PWD}":/home/jovyan/work rpersee/semantic-web-notebook
```

In your notebook, load the Jupyter-RDFify extension:
```
%reload_ext jupyter-rdfify
```

Use the Jupyter-RDFify magic command `%rdf`:
```
%rdf --help
```

Get full examples here: [SemWebNotebooks/Notebooks](https://github.com/SemWebNotebooks/Notebooks/tree/main/Notebooks).

