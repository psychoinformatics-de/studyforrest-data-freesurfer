High-resolution structural images were used to generate the cortical surfaces
using FreeSurfer (v5.3.0, freely available at http://surfer.nmr.mgh.harvard.edu,
[Dale et al., 1999]). Additional high-resolution T2w images were included
in the reconstruction (recon-all -T2 t2file).

The surface quality was checked by inspecting the slice screenshots of QATool
(v1.1, freely available at http://ftp.nmr.mgh.harvard.edu/fswiki/QATools, [no
source paper linked]). The QATool was adopted to take sreenshots of the
high-resoluton pial surface.


DataLad datasets and how to use them
====================================
This repository is a DataLad (https://www.datalad.org/) dataset.
It provides fine-grained data access down to the level of individual files,
and allows for tracking future updates.
In order to use this repository for data retrieval, DataLad (https://www.datalad.org/)
is required. It is a free and open source command line tool, available for all
major operating systems, and builds up on Git and git-annex
(https://git-annex.branchable.com/) to allow sharing, synchronizing, and version
controlling collections of large files. You can find information on how to install
DataLad at http://handbook.datalad.org/en/latest/intro/installation.html.

Get the dataset
===============
A DataLad dataset can be “cloned” by running

        ‘datalad clone <url>’.

Once a dataset is cloned, it is a light-weight directory on your local machine.
At this point, it contains only small metadata and information on the identity
of the files in the dataset, but not actual content of the (sometimes large) data files.

Retrieve dataset content
========================
After cloning a dataset, you can retrieve file contents by running

        ‘datalad get <path/to/directory/or/file>’

This command will trigger a download of the files, directories, or subdatasets
you have specified.

DataLad datasets can contain other datasets, so called “subdatasets”.
If you clone the top-level dataset, subdatasets do not yet contain metadata and
information on the identity of files, but appear to be empty directories.
In order to retrieve file availability metadata in subdatasets, run

        ‘datalad get -n <path/to/subdataset>’

Afterwards, you can browse the retrieved metadata to find out about subdataset
contents, and retrieve individual files with datalad get.
If you use ‘datalad get <path/to/subdataset>’, all contents of the subdataset
will be downloaded at once.

Stay up-to-date
===============
DataLad datasets can be updated. The command ‘datalad update’ will “fetch” updates
and store them on a different branch (by default ‘remotes/origin/master’).
Running

        ‘datalad update –merge’

will “pull” available updates and integrate them in one go.

More information
================
More information on DataLad and how to use it can be found in the DataLad Handbook at http://handbook.datalad.org/en/latest/index.html. The chapter “DataLad datasets” can help you to familiarize yourself with the concept of a dataset.




References
----------

Dale, A.M., Fischl, B., Sereno, M.I., 1999. Cortical surface-based analysis. I.
Segmentation and surface reconstruction. Neuroimage 9, 179-194.