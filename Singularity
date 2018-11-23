BootStrap: docker
From: conda/miniconda2

%label
    Maintainer remi-andre.olsen@scilifelab.se

%post
    apt-get update
    apt-get install -y git build-essential libboost1.62-all-dev zlib1g-dev sed
    cd /opt
    conda install networkx
    git clone https://github.com/machinegun/SALSA.git 
    cd SALSA
    make

    for i in *.py; do sed -i "1s/^/#\!\/usr\/bin\/env python\n/" $i; done
    for i in *.py; do chmod +x $i; done
    mv break_contigs /bin
    mv break_contigs_start /bin
    mv correct_links /bin
    mv *.py /bin 
    apt-get clean
    rm -rf /var/lib/apt/lists/*


