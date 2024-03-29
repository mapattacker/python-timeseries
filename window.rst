Window Slicing
===============

One of the ways to analyse timeseries is through the comparison of the data between windows of time.

Slider
-------
We can use keras's ``TimeseriesGenerator`` to quickly obtain a window slider across a timeseries. 
This function is meant for RNN supervised training, hence require a y data input. 
However, we can use ``np.zeros`` to create a dummy y data.

.. code:: python

    import numpy as np

    X = np.array(df['original'])
    y = np.zeros(len(sig))


    from keras.preprocessing.sequence import TimeseriesGenerator

    win_length=17000
    win_slide=5000
    batch=(len(X)-win_length)/win_slide

    data = TimeseriesGenerator(X, y,
                                length=win_length,
                                sampling_rate=1,
                                stride=win_slide,
                                batch_size=batch)[0]

    X = data[0]
    y = data[1]

Split by Period
---------------
If each wave or period is consistent over time, i.e., operational hours we can split a dataframe by 
datetime.

.. code:: python

    # split by each day
    result = [group[1] for group in df.groupby(df['Timestamp'].dt.date)]

