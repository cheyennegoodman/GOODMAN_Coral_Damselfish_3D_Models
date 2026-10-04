Last edit: 10/04/2026
Last editor: Lila Goodman

## Project Structure for 3d Models

```         
./
├── analysis_params.yaml          # Base analysis parameters template
├── docs/                         # Documentation files
│   ├── api_1july.txt            # API documentation
│   └── metashape_python_api_2_1_1.pdf
├── examples/                     # Example project directories (local)
├── images/                       # Supporting images (eg. for RMD rendering)
├── presets/                      # Software preset files
│   ├── lightroom/               # Adobe Lightroom presets
│   │   └── step0_lightroom_hdrphoto_r5c.xmp
│   └── premiere/                # Adobe Premiere presets
│       └── step0_premierepro_uhd_8k_23sept2024.epr
├── LilasThesis/                      # 3d modeling for thesis
│   ├── April3d/               # Project directory April's 3D models
│   │   └── output            # final output
│   │   └── processing        # 3d models 
│   │   |   └── frames # .tiff files of April's models 
│   │   |   └── psxraw # .psx and .files for every plot processed for April
│   │   |   └── reportsraw # pdf of each plot's raw report 
│   │   └── video_source # videos of April's models
│   │   └── analysis_params.yaml
│   │   └── status_April3d.csv # progress document for April 3d models
│   └── June263d/               # Project directory June's 2026 3D models
│   │   └── output            # final output
│   │   └── processing        # 3d models 
│   │   |   └── frames # .tiff files of June's 2026 models 
│   │   |   └── psxraw #.psx and .files for every plot processed for June 2026
│   │   |   └── reportsraw # pdf of each plot's raw report 
│   │   └── video_source # videos of June's 2026 models
│   │   └── analysis_params.yaml
│   │   └── status_June263d.csv # progress document for June 2026 3d models
│   └── June3d/               # Project directory June 2025's 3D models
│   │   └── output            # final output
│   │   └── processing        # 3d models 
│   │   |   └── frames # .tiff files of June's 2025 models 
│   │   |   └── psxraw #.psx and .files for every plot processed for June 2025
│   │   |   └── reportsraw # pdf of each plot's raw report 
│   │   └── video_source # videos of June's 2025 models
│   │   └── analysis_params.yaml
│   │   └── status_June3d.csv # progress document for June 2025 3d models
│   └── May3d/               # Project directory May's 3D models
│   │   └── output            # final output
│   │   └── processing        # 3d models 
│   │   |   └── frames # .tiff files of May's models 
│   │   |   └── psxraw # .psx and .files for every plot processed for May
│   │   |   └── reportsraw # pdf of each plot's raw report 
│   │   └── video_source # videos of May's models
│   │   └── analysis_params.yaml
│   │   └── status_May3d.csv # progress document for May 3d models
├── src/                          # Source code
│   ├── config.py                # Configuration loading utilities
│   ├── step0.py                 # Frame extraction
│   ├── step1.py                 # Initial 3D processing (most time-consuming)
│   ├── step2.py                 # Chunk management/consolidation
│   ├── step3.py                 # Model processing (automatic scaling)
│   ├── step3_manualScale.py     # Model processing (manual scaling)
│   ├── step4.py                 # Final exports & web publishing
│   ├── legacy/                  # Legacy/archived scripts
│   └── utility/                 # Utility scripts
│       ├── enumerate_gpus.py    # GPU detection for Metashape
│       ├── reset_full.py        # Complete project reset
│       ├── reset_step1.py       # Reset preserving Steps 0&1
│       └── file_naming.py       # Standardized file naming functions
├── venv312/                          # virtual environment for python 3.12
│   ├── config.py                # Configuration loading utilities
├── readme.md                     # Workflow Review
├── modelinfo.Rmd                 # This documentation
└── requirements.txt              # Python package dependencies
```
## IMPORTANT NOTES 

1.  File name convention for models are "[MODEL#]_psx[x]_{DATE}.psx" and "[MODEL#]_psx[x]_{DATE}.files". [x] represents if this was included in the 1st or 2nd batch of the run.  

2. Models had to be manually checked for alignment and frame quality. Frame extraction led to repeating frames the plots that would interfere with Metashape's ability to align photos in the python's script. 

3. These models were processed under a time limit through a University's desktop. Models could not run over night and had to be run in separate batches for library employees to utilize the desktop throughout the day. Batches will override themselves if not renamed after step3.py. This only includes same day batches. 

4. All models need to be manually scaled (doing that right now)
