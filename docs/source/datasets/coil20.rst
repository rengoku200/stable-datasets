COIL-20
=======

Overview
--------

.. image:: teasers/coil20_teaser.png
   :align: center
   :width: 90%

COIL-20 contains 1,440 grayscale images of 20 objects. Each object was
photographed from 72 views. The processed images are 128 × 128 pixels.

The source dataset does not provide an official train/test split. The
``train`` split in this builder contains all 1,440 images.

Data Structure
--------------

Each ``ds[i]`` returns:

.. list-table::
   :header-rows: 1

   * - Key
     - Type
     - Description
   * - ``image``
     - ``PIL.Image.Image``
     - 128 × 128 grayscale image
   * - ``label``
     - ``int``
     - Object class ID from 0 to 19
   * - ``view_id``
     - ``int``
     - View identifier read from the source filename

Usage Example
-------------

.. code-block:: python

    from stable_datasets.images import COIL20

    ds = COIL20(split="train")
    print(len(ds))  # 1440

    sample = ds[0]
    print(sample["image"].size, sample["label"], sample["view_id"])

Source and Citation
-------------------

- Source: https://www.cs.columbia.edu/CAVE/software/softlib/coil-20.php
- S. A. Nene, S. K. Nayar, and H. Murase, *Columbia Object Image Library
  (COIL-20)*, Columbia University Technical Report CUCS-005-96, 1996.