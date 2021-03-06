---
title: 'corr.axes'
tags: 'commands'
redirect_from: '/wiki/Corr.axes.html'
---
The **corr.axes** command will calculate the
correlation coefficient for each column in a shared/relabund file to the
axes displayed in a pcoa file.


## Default settings

The **corr.axes** command reads a shared, relabund
or metadata file as well as an axes file. If a shared file is given, the
relabund is calculated. A metadata file has the same number of rows as
samples, but the column(s) are floats that describe the samples (e.g.
temperature, weight, etc.)

    mothur > corr.axes(shared=genus.pool.shared, axes=genus.pool.thetayc.genus.lt.pcoa)

or

    mothur > corr.axes(relabund=genus.pool.relabund, axes=genus.pool.thetayc.genus.lt.pcoa)

or

     mothur > corr.axes(metadata=genus.pool.metadata, axes=genus.pool.thetayc.genus.lt.pcoa)

## Options

### groups

The groups parameter allows you to specify which of the groups you would
like included. The group names are separated by dashes. By default all
groups in the shared or relabund file are used.

### label

The label parameter allows you to select what distance level you would
like used, if none is given the first distance is used.

### method

The method parameter allows you to select what method you would like to
use. Options are [pearson](https://en.wikipedia.org/wiki/Pearson_correlation_coefficient) (default), [spearman](https://en.wikipedia.org/wiki/Spearman's_rank_correlation_coefficient) and [kendall](https://en.wikipedia.org/wiki/Kendall_tau_rank_correlation_coefficient).

To use the spearman method:

    mothur > corr.axes(metadata=genus.pool.metadata, axes=genus.pool.thetayc.genus.lt.pcoa, method=spearman)

or to use the kendall method:

    mothur > corr.axes(metadata=genus.pool.metadata, axes=genus.pool.thetayc.genus.lt.pcoa, method=kendall)

### numaxes

The numaxes parameter allows you to select the number of axes you would
like to use. Default=3.

    mothur > corr.axes(metadata=genus.pool.metadata, axes=genus.pool.thetayc.genus.lt.pcoa, numaxes=2)

## Revisions

-   1.24.0 - added p\_values.
-   1.25.0 - fixed OTU labels.
-   1.40.0 - Speed and memory improvements for shared files.
    [\#357](https://github.com/mothur/mothur/issues/357) ,
    [\#347](https://github.com/mothur/mothur/issues/347)
-   1.44.0 - Fixes **corr.axes** bug when metadata files contain zeroed
    columns.
