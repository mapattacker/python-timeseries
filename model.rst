Modelling
==============

Agglomerative Clustering
-------------------------
Agglomerative Clustering is a type of *hierarchical clustering* technique 
used to build clusters from bottom up. 
Divisive Clustering is the opposite method of building clusters from top down, 
which is not available in sklearn.


.. code:: python

    from scipy.cluster.hierarchy import linkage, dendrogram

If we have a lot of datapoints, the plotted dendrogram will look overwhelmingly cluttered, like below.

.. figure:: images/dendrogram1.png
    :width: 700px
    :align: center

The dendrogram can be further enhanced by 
 * adding title and axis labels
 * truncating the bottom branches
 * labelling each cluster split distance
 * a horizontal line to investigate where would be an appropriate cutoff point

.. figure:: images/dendrogram2.png
    :width: 500px
    :align: center