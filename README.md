#Neuronux: Brain Tumor Segmentation & 3D Visualization
Neuronux is a deep learning-based project for brain tumor segmentation and 3D visualization using MRI scans.

2D U-Net is used for accurate tumor segmentation on MRI slices.
Marching Cubes algorithm is applied on the segmentation masks to create a 3D surface mesh, enabling interactive visualization of tumor boundaries.
This project aims to help in medical imaging by providing both slice-wise tumor localization and intuitive 3D visualization for better analysis.

🚀 Features
Preprocessing: Normalization, resizing, and augmentation of MRI slices.
Segmentation: 2D U-Net trained on MRI slices for tumor boundary detection.
Post-processing: Binary masks of tumors extracted.
3D Reconstruction: Marching Cubes algorithm converts voxel grids into triangular meshes.
Visualization: Interactive 3D rendering using Plotly.

🧬 How It Works
Input Data (MRI Scans):
MRI volumes are treated as stacks of 2D slices.
Each slice is fed into the 2D U-Net model.
Segmentation (2D U-Net):
Produces binary masks per slice (tumor vs. non-tumor).
Mask threshold: 0.5 (pixel classified as tumor if probability ≥ 0.5).
Voxel Grid Formation:The 2D slice masks are stacked together → forming a 3D voxel grid (where each voxel is like a 3D pixel).
Marching Cubes (3D Surface Extraction): Scans the voxel grid cube-by-cube (each cube = 8 voxels).
If intensity crosses threshold (0.5 in this case), triangular meshes are generated.Output = 3D tumor surface mesh.
Visualization:  Mesh rendered with Plotly → allows rotation, zoom, and exploration of tumor shape.
