We want to identify extreme observations, Detecting outliers is unfortunately more of an art than a science. However, a common method is to
assume the data is normally distributed and based on that assumption “draw” an ellipse around the data,
classifying any observation inside the ellipse as an inlier (labeled as 1) and any observation outside the
ellipse as an outlier (labeled as -1), In the above arrays, values of -1 refer to outliers whereas values of 1 refer to inliers. A major limitation
of this approach is the need to specify a contamination parameter, which is the proportion of
observations that are outliers—a value that we don’t know. Think of contamination as our estimate of
the cleanliness of our data. If we expect our data to have few outliers, we can set contamination to
something small. However, if we believe that the data is very likely to have outliers, we can set it to a
higher value.
Instead of looking at observations as a whole, we can instead look at individual features and identify
extreme values in those features using interquartile range (IQR), IQR is the difference between the first and third quartile of a set of data. You can think of IQR as the
spread of the bulk of the data, with outliers being observations far from the main concentration of data.
Outliers are commonly defined as any value 1.5 IQRs less than the first quartile or 1.5 IQRs greater
than the third quartile, There is no single best technique for detecting outliers. Instead, we have a collection of techniques all
with their own advantages and disadvantages. Our best strategy is often trying multiple techniques (e.g.,
both EllipticEnvelope and IQR-based detection) and looking at the results as a whole.
If at all possible, we should take a look at observations we detect as outliers and try to understand them.
For example, if we have a dataset of houses and one feature is number of rooms, is an outlier with 100
rooms really a house or is it actually a hotel that has been misclassified.
