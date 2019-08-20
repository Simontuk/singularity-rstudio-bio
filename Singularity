BootStrap: shub
From: Simontuk/singularity-rstudio

%labels
  Maintainer Simon Steiger
  RStudio_Version 1.2.1335

%help
  This will run RStudio Server

%apprun rserver
  exec rserver "${@}"

%runscript
  exec rserver "${@}"

%environment
  export PATH=/usr/lib/rstudio-server/bin:${PATH}

%post
  yum update

  Rscript -e "install.packages(c('devtools','tidyverse','ape','Seurat'))"
  Rscript -e "devtools::install_github(c('satijalab/Seurat',
                                            'immunogenomics/presto',
                                            'jokergoo/ComplexHeatmap',
                                            'hhoeflin/hdf5r'))"
  
  #Cleanup yum
  yum clean all