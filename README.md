# GKDE

GKDE (Multi-GPU Kernel Density Estimation)

A multi-GPU code for data-intensive kernel density estimation (KDE). Spatial computational domain is first estimated for KDE. Then the study area is decompose into sub-regions through an adaptive partitioning approach. Each sub-region is processed by a GPU node. These GPU nodes are communicated through massage passing interface (MPI).

To compile:
First, change the CUDA_PATH at the begining of your src/Makefile to your CUDA directory. Then run make in src directory.

To run:
mpirun -np number_of_GPU_nodes ./MultiGPUKDE input_data output_file_name(GEOTIFF) xMin xMax yMin yMax cell_size kernel_bandwidth number_of_nodes_in_x_dimension number_of_nodes_in_y_dimension

input_data: A CSV file with no leader and only two column: x-coordinate and y cooridinate. Each row represent one input point

Example: 
mpirun -np 2 ./MultiGPUKDE data/SampleData.csv /gpfs_scratch/tsccsj/KDE/sampleResult21.tif -2380000 2280000 -1520000 1420000 2000 20000 2 1

Contact:
CyberInfrastructure and Geospatial Information (CIGI) Laboratory
269 Computing Applications Building M-C 150 
605 East Springfield Avenue
Champaign, IL, USA 61820
Office: (+1)217-244-9315
Fax: (+1)217-244-1785

Major developers:
Yizhao Gao (ygao29@illinois.edu)

