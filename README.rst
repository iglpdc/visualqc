==========
visualqc
==========


.. image:: https://img.shields.io/pypi/v/visualqc.svg
        :target: https://pypi.python.org/pypi/visualqc

.. image:: https://img.shields.io/travis/raamana/visualqc.svg
        :target: https://travis-ci.org/raamana/visualqc

.. image:: https://readthedocs.org/projects/visualqc/badge/?version=latest
        :target: https://visualqc.readthedocs.io/en/latest/?badge=latest
        :alt: Documentation Status

.. image:: https://pyup.io/repos/github/raamana/visualqc/shield.svg
     :target: https://pyup.io/repos/github/raamana/visualqc/
     :alt: Updates

Tool to automate the quality control of MRI segmentations (gray and white matter, cortical, subcortical and other arbitrary segmentations) produced by Freesurfer and other tools.

.. image:: docs/vqc_logo_small.png

Assessing and guranteeing the accuracy of any automatic segmentation (be it gray or white surfaces for cortical thickness, or a subortical segmentation) requires manual visual inspection. Not just one slice. Or one view. But many slices in all the views to ensure the 3d segmentation is accurate at the voxel-level. This process, in its most banal form, is quite cumbersome and time-consuming. Without any assistive tool, it requires opening both the MRI and segmentation for one subject in an editor that can overlay and color them properly, and manually reviewing one slice at a time, navigate through many many slices, and record your rating in a spreadsheet. And repeat this process for multiple subjects. In some even more demanding tasks (such as assessing the accuracy of cortical thickness e.g. generated by Freesurfer), you may need to review multiple types of visualizations, such as surface-redering with different labels colored appropriately, in addition to voxel-wise overlay on MRI. Without an automatic tool, this process allows too many human mistakes, over the span of 100s of subjects over many weeks jumping through multiple visualization software and spreadsheets. ``visualqc`` aims to reduce that to a single command to seamlessly record the ratings of accuracy and navigate through 100s of subjects with ease. All you need to do is sit back, focus your exper eye on the accuracy and ``visualqc`` takes care of the flow and bookkeeping.

Neuroimagers familiar with `ENIGMA quality control (QC) protocols <http://enigma.ini.usc.edu/protocols/imaging-protocols/>`_ would especially find this tool much easier. In addition to integrating valuable experience and knowledge from those protocols, this tool makes it easy so you don't have to deal with multiple scripts (to generate images and combine visualizations), and no alternating between multiple spreadsheets to keep track of ratings. Additional advantages include zooming in and needing to use only a single tool to QC both cortical and subcortical segmentations.

* Free software: MIT license
* Documentation: https://visualqc.readthedocs.io.


Features
--------

* Makes the review and rating workflow seamless and easy! It is simple as: visualize the auto-generated overlay, review, zoom-in wherever you need, rate the quality, and proceed to next!
* Display multiple slices in multiple views, and easily navigate all subjects in a dataset
* Allows you to zoom in to any view/slice to ensure you won't miss any detail
* Allows you to control the transparency of overlay to your expert preference
* Allows to focus on a single or a set of arbitrary segmentations (hippocampus, or PCG or DMN etc) if necessary
* Automatically detect and flag outliers (coming soon)

Gallery (contour)
-----------------

Some examples of how the interface looks are shown below. The first screenshot showcases the use case wherein we can review the accuracy of Freesufer's cortical parcellation against the original MRI (note that only one view is shown and one panel is zoomed-in):

.. image:: docs/vis/contour/visual_qc_cortical_contour__Pitt_0050034_v1_ns18_4x6.png

In the second screenshot, we show the use case for a single label (subcortical segmentation, tissue class or cortical ROI) - shown here are hippocampus and amygdala:

.. image:: docs/vis/contour/visual_qc_labels_contour_53_Pitt_0050039_v012_ns18_9x6.png

We can also add nearby amygdala:

.. image:: docs/vis/contour/visual_qc_labels_contour_53_54_Pitt_0050036_v02_ns21_6x7.png

And you can add as many ROIs as you like:

.. image:: docs/vis/contour/visual_qc_labels_contour_10_11_12_13_NYU_0051036.png

ROIs could be from anywhere in the MRI (including big cortical labels too!). For example, let's look at Insula (label 1035 in Freesurfer ColorLUT) in the left hemi-sphere :

.. image:: docs/vis/contour/visual_qc_labels_contour_1035_Pitt_0050032_v02_ns21_6x7.png

And, how about middle temporal?

.. image:: docs/vis/contour/visual_qc_labels_contour_2015_Pitt_0050035_v02_ns21_6x7.png

Let's just focus on axial view to get more detail:

.. image:: docs/vis/contour/visual_qc_labels_contour_2015_Pitt_0050039_v2_ns27_3x9.png
