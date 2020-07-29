# location matching spike

## Experiments

Experiments to conduct

1. a means of programmatically identify a geographical coverage based on postcode centroid
2. an efficient means of ranking matches by location

### Location Bounding

This is a two-part challenge: the first of which could / should run as a batch.

1. Given a postcode, identify postcode centroids within 50km distance \(configurable\)
2. Given a postcode, return a true/false for in/out of bounds.

Needs:

* [Code-Point Open data source](https://osdatahub.os.uk/downloads/open/CodePointOpen)

Side-effects:

* postcode validation

### Location Ranking

Challenge: Given a source location and a set of target locations, rank the geographical fitness

The source represents someone wishing to see how many geographical matches they may have. The targets represent the potential matches.

Critical measurement: time taken to match. This should be relatively independent of number of potential targets in the dataset.

Ranking should be on scale of 0–1, with 1 being a perfect match.

Question: is perfect a geographical identity \(so I will only ever match someone with the same postcode as me\), or is it the best possible match. What if this is a long way away? How does the scale fade away to 0? Is that a bounded figure?

Needs:

* test data sets derived from postcodes
* large geographical \(target\) data set
* run tests multiple times and with varying numbers in target. Plot results.

## Effort estimate

* Location bounding feels like a day's solid effort
* Location ranking feels like 1-2 days.

This is effort, not elapsed time. Given need to contribute to ongoing dev and other meetings, this is estimated at a week's elapsed time.

