# Graph Representation Learning of Longitudinal Medical Imaging Trajectories for Treatment Response Prediction

**Johannes Kiechle<sup>1,2,3,6</sup>**, Richard Osuala<sup>2,4</sup>, Daniel M. Lang<sup>3</sup>, Stefan M. Fischer<sup>1,2,3,7</sup>, Ivana Janíčková<sup>5</sup>, Karim Lekadir<sup>4</sup>, Julia A. Schnabel<sup>1,3,6,7,\*</sup> and Jan C. Peeken<sup>2,\*</sup>

<sup>1</sup> Technical University of Munich, Germany |
<sup>2</sup> TUM Klinikum Rechts der Isar, Munich, Germany |
<sup>3</sup> Helmholtz Munich, Germany |
<sup>4</sup> Universitat de Barcelona |
<sup>5</sup> Medical University of Vienna |
<sup>6</sup> King's College London, United Kingdom |
<sup>7</sup> Munich Center for Machine Learning |
<sup>\*</sup> Shared Senior Authorship 

[Paper](https://arxiv.org/pdf/2607.04912) | [MICCAI GRAIL](https://grail-miccai.github.io/)

<p align="center">
  <img src="./figures/method.png" width="900"/>
</p>

**Abstract:** In patients with breast cancer, pathological complete response (pCR) has been established as a clinically meaningful surrogate marker for long-term outcomes. While commonly treated with neoadjuvant chemotherapy (NACT), effective treatment decision-making remains challenging, as therapeutic response can vary substantially across patients, calling for predictive models capable of accurately estimating individualized treatment response. To address this, we propose an imaging-based 3D spatio-temporal framework for treatment response prediction that integrates a state-of-the-art graph neural network with relational modeling of temporal interactions across timepoints alongside three novel complementary self-supervised treatment trajectory representation learning objectives. 

Experiments across a cohort of 585 patients from the public ISPY-2 dataset demonstrate that our method substantially outperforms both vision and self-supervised learning baselines across several classification metrics. Alongside establishing a breast cancer pCR prediction benchmark, we include a principled ablation of our method and further introduce and empirically assess the impact of the available number of DCE-MRI timepoints per patient trajectory and the inclusion of inter-scan time-differences. Overall, our study substantiates the utility of clinically meaningful longitudinal medical imagaging modeling for predicting NACT-induced pCR.

**Keywords:** GNNs · Longitudinal · Self-Supervised · Breast Cancer

## Dataset

#### Install Python PyPI Package
```bash
$ pip install ISPY2-pCR-dataset
```

#### Create Python script
```python
from ISPY2_pCR_dataset import download_and_preprocess

if __name__ == "__main__":

    download_dir = "/path/to/output/directory"
    manifest_file_path = "/path/to/manifest_xlsx/file" # can be found at https://github.com/hannesk95/ISPY2-pCR-dataset/tree/main/data
    clinical_file_path = "/path/to/clinical_xlsx/file" # can be found at https://github.com/hannesk95/ISPY2-pCR-dataset/tree/main/data

    download_and_preprocess(
        download_dir=download_dir,
        manifest_file_path=manifest_file_path,
        clinical_file_path=clinical_file_path
        )
```

#### Start a tmux session and run the Python script. This will take a while!

```bash
$ tmux
$ python ispy2_pcr_dataset.py
```

#### Once the script has finished, you'll find the final dataset at
```bash
$ cd download_dir/processed_data
```

## Citation

```bibtex
@article{kiechle2026graph,
title={Graph Representation Learning of Longitudinal Medical Imaging Trajectories for Treatment Response Prediction},
author={Kiechle, Johannes and Osuala, Richard and Lang, Daniel M and Fischer, Stefan M and Jan{\'\i}{\v{c}}kov{\'a}, Ivana and Lekadir, Karim and Schnabel, Julia A and Peeken, Jan C},
journal={arXiv preprint arXiv:2607.04912},
year={2026}
}
```

**[INFO] Full source code will be released upon publiction.**

