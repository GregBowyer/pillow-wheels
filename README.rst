Pillow OS X Wheel Builder
=========================

This repository creates wheels for tagged versions of Pillow::

    git submodule init
    git submodule update
    git add Pillow
    cd Pillow
    git checkout <VERSION>
    cd ..
    git commit -a -m "<VERSION> wheels"
    git push

.. image:: https://img.shields.io/travis/python-pillow/pillow-wheels/latest.svg?label=OS%20X%20build
   :target: https://travis-ci.org/python-pillow/pillow-wheels
   :alt: Travis CI build status (OS X)

Dependencies
------------

NumPy
~~~~~

Check minimum NumPy versions to build against in ``.travis.yml`` file. Build against the earliest NumPy that Pillow is compatible with; see `forward, backward numpy compatibility <http://stackoverflow.com/questions/17709641/valueerror-numpy-dtype-has-the-wrong-size-try-recompiling/18369312#18369312>`_

Wheels
------

Wheels are uploaded to a `rackspace container <http://cdf58691c5cf45771290-6a3b6a0f5f6ab91aadc447b2a897dd9a.r50.cf2.rackcdn.com/>`_. Credentials for this container are encrypted to this specific repo in the ``.travis.yml`` file, so the upload won't work from another repository.

PyPI
~~~~

Download wheels from Rackspace::

    wget -m -A 'Pillow-<VERSION>*' \
    http://cdf58691c5cf45771290-6a3b6a0f5f6ab91aadc447b2a897dd9a.r50.cf2.rackcdn.com

Upload wheels to PyPI::

    cd cdf58691c5cf45771290-6a3b6a0f5f6ab91aadc447b2a897dd9a.r50.cf2.rackcdn.com
    twine upload Pillow-<VERSION>*
