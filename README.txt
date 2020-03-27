This directory is one of three test directories called data-01, data-05, data-10 which
is being used to test the docker image, 

	rocdatascience.azurecr.io/rraqueno/rdsc-imagemagick-identify-test

The three directories contain the first 01, 05, and 10 images of the the CelebA data set.

The docker image contains its own /data directory which can be overridden for resulting
docker containers using a form of the following "docker run".

	docker run -it --mount type=bind,source=$PWD/data-05,target=/data --name data-test-05 		rdsc-imagemagick-identify-test

The test can be invoked by simply giving the "make" command at the default working directory
and a file called identify-results.txt will be created in the data directory containing a
the images.  If an answers directory exists, diff command will be invoked to compare the 
resulting identify-results.txt and the data/identify-results.txt

RR

27-MAR-2020
