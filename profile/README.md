<div align="center">
  <img src="https://raw.githubusercontent.com/Starlitnightly/ImageStore/main/omicverse_img/firstpage.webp" alt="omicverse banner" width="720"/>

  <h1>omicverse</h1>

  <p><strong>A unified Python framework for bulk, single-cell, and spatial omics analysis.</strong></p>

  <p>
    <a href="https://pypi.org/project/omicverse/"><img src="https://img.shields.io/pypi/v/omicverse" alt="PyPI"></a>
    <a href="https://anaconda.org/conda-forge/omicverse"><img src="https://img.shields.io/conda/dn/conda-forge/omicverse?logo=Anaconda" alt="conda-forge"></a>
    <a href="https://omicverse.readthedocs.io"><img src="https://readthedocs.org/projects/omicverse/badge/?version=latest" alt="Docs"></a>
    <a href="https://doi.org/10.1038/s41467-024-50194-3"><img src="https://img.shields.io/badge/DOI-10.1038%2Fs41467--024--50194--3-368650.svg" alt="DOI"></a>
    <a href="https://scverse.org"><img src="https://img.shields.io/badge/scverse-ecosystem-blue.svg?labelColor=yellow" alt="scverse"></a>
    <a href="https://www.gnu.org/licenses/gpl-3.0"><img src="https://img.shields.io/badge/license-GPL--3.0-blue.svg" alt="License"></a>
  </p>
</div>

---

## About

**omicverse** is a scverse-compatible toolkit that unifies **bulk RNA-seq**, **single-cell**, **spatial transcriptomics**, and **multi-omics** analysis under one Python API — from raw counts to deep generative modelling, trajectory inference, cell–cell communication, and downstream visualization.

This organization hosts the main package alongside supporting libraries for out-of-memory I/O, tutorials, and benchmarking.

## Flagship repositories

| Repo | What it does |
|------|--------------|
| [**omicverse**](https://github.com/omicverse/omicverse) | Main package — preprocessing, integration, single-cell, spatial, multi-omics |
| [**omicverse-tutorials**](https://github.com/omicverse/omicverse-tutorials) | End-to-end notebooks for every supported workflow |
| [**anndataoom**](https://github.com/omicverse/anndataoom) | Out-of-memory AnnData wrapper on top of `anndata-rs` for million-cell datasets |

## Quick start

```bash
pip install -U omicverse
```

```python
import omicverse as ov

adata = ov.read("data.h5ad")
ov.pp.preprocess(adata, n_top_genes=3000)
ov.pp.pca(adata, n_comps=50)
ov.pl.embedding(adata, basis="umap", color="cell_type")
```

For large datasets, load out-of-memory:

```python
adata = ov.read("big.h5ad", backend="rust")   # via anndataoom / anndata-rs
```

Browse the [full tutorial set](https://omicverse.readthedocs.io/en/latest/Tutorials/) for bulk, single-cell, spatial, and multi-omics workflows.

## Citation

If omicverse helps your research, please cite:

> Zeng, Z., Ma, Y., Hu, L. *et al.* **OmicVerse: a framework for bridging and deepening insights across bulk and single-cell sequencing.** *Nature Communications* **15**, 5983 (2024). <https://doi.org/10.1038/s41467-024-50194-3>

## Community

- [Report an issue](https://github.com/omicverse/omicverse/issues)
- [Discussions](https://github.com/omicverse/omicverse/discussions)
- [Contribution guide](https://github.com/omicverse/omicverse/blob/main/CONTRIBUTING.md)

---

Part of the [**scverse**](https://scverse.org) ecosystem.
