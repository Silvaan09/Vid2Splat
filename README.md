# vid2splat

Turn a phone video into a 3D Gaussian Splatting scene, with the camera poses estimated by a
visual odometry / SfM pipeline written from scratch instead of COLMAP.

> **Status:** work in progress. Results, demo and viewer link will be added here.

This repository ties together two standalone projects, included as git submodules:

| Repo | What it does |
|---|---|
| [vid2sfm](https://github.com/Silvaan09/vid2sfm) | Video → camera poses + sparse point cloud, exported in COLMAP format |
| [sfm2splat](https://github.com/Silvaan09/sfm2splat) | COLMAP-format scene → trained Gaussian Splatting scene, with evaluation |

The COLMAP file format is the contract between them, so either side can be swapped: COLMAP can
stand in for `vid2sfm` as the reference pose source, and any splatting code can read what
`vid2sfm` writes.

## Getting the code

```bash
git clone --recurse-submodules https://github.com/Silvaan09/vid2splat.git
```

If you cloned without `--recurse-submodules`:

```bash
git submodule update --init
```

Setup instructions are in each submodule's README.
