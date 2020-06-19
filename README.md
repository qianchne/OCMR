# OCMR (v1.0) 
## Open-Access Repository for Multi-Coil k-space Data for Cardiovascular Magnetic Resonance Imaging

Cardiovascular MRI (CMR) is a non-invasive imaging modality that provides excellent soft-tissue contrast without the use of ionizing radiation. The limited efficiency of MRI data acquisition and physiological motions necessitate data undersampling. Recovering diagnostic quality CMR images from highly undersampled data has been active area of research, and several data acquisition and processing methods have been proposed to accelerate CMR. Platforms to objectively evaluate and compare different processing methods can expedite innovation and promote clinical translation of these methods. In this work, we introduce an open-access repository, called OCMR, that provides multi-coil k-space data from 53 fully sampled and 212 prospectively undersampled cardiac cine series. The fully sampled datasets are intended for quantitative comparison and evaluation of image reconstruction methods. The free-breathing, prospectively undersampled datasets are intended to qualitatively evaluate the performance and generalizability of the reconstruction methods. The datasets were collected on three Siemens Magnetom scanners: Prisma (3T), Avanto (1.5T) and Sola (1.5T). The data from the OCMR repository can be downloaded from the link on www.ocmr.edu. Each dataset is assigned eight attributes, which allows downloading a subset of the datasets.

## Download OCMR Data 
Download data from the OCMR repository from the link on this page www.ocmr.edu. Below are the instructions to read OCMR data into Matlab and Python, respectively. After running the code, it will generate a nine-dimensional array, kData, for the k-space data and a structure, param, that captures acquisition parameters.

## Read Data Using Matlab
### Step 1: Download wrapper
Download read_ocmr.m and example_ocmr.m from https://github.com/MRIOSU/OCMR/tree/master/Matlab.
### Step 2: Download ISMRMRD libraries
Download ISMRMRD libraries from https://github.com/ismrmrd/ismrmrd/tree/master/matlab/%2Bismrmrd. 
### Step 3: Read the Data
Place read_ocmr.m, example_ocmr.m, and the entire ‘/+ismrmrd’ subfolder in one folder. Execute example_ocmr.m in Matlab.

## Read Data Using Python
### Step 1: Download wrapper
Download 'read_ocmr.py' and 'example_ocmr.ipynb' from https://github.com/MRIOSU/OCMR/tree/master/Python.
### Step 2: Install ISMRMRD libraries
Install ismrmrd-python from https://github.com/ismrmrd/ismrmrd-python and ismrmrd-python-tools from https://github.com/ismrmrd/ismrmrd-python-tools. For help, see the Jupyter Notebook entry 'example\_ocmr.ipynb' from the previous Step.
### Step 3: Read the Data
Place 'read_ocmr.py' and 'example_ocmr.ipynb' in one folder. Modify the 'filename' as needed, and run the example in 'example_ocmr.ipynb'.

## Data Structure
Once a dataset is read into Matlab or Python, it yields the k-space array, kData, and a structure, param. The kData array has nine dimensions: [kx, ky, kz, coil, phase, set, slice, rep, avg], which represent frequency encoding, first phase encoding, second phase encoding, coil, phase (time), set (velocity encoding), slice, repetition, and number of averages, respectively. For example, a cine stack with frequency encoding size 160, phase encoding size 120, number of coils 18, number of frames 60, number of slices 10 will generate kData with these dimension: 160x120x1x18x60x1x10x1x1. The second output, param, provides pertinent acquisition parameters. For example, param.FOV, param.TRes, param.flipAngle_deg, param.sequence_type specify field-of-view, temporal resolution, flip angle, and the type of sequence, respectively.

## Anonymization
All ISMRMRD datasets included in OCMR have been de-identified, where Protected Health Information (PHI) as well as scan date and location have been removed. All datasets have been manually inspected to ensure that identifying facial features are not included.

## Future Directions
The current version (v1.0) of OCMR only includes cardiac cine data. We intend to progressively expand the size of cardiac cine data and include additional CMR applications, including 2D phase-contrast MRI.

## Contact Information
For help with downloading and reading the data, contact Chong Chen (chen.7211@osu.edu); for feedback or questions about the OCMR repository, contact Rizwan Ahmad (ahmad.46@osu.edu)
