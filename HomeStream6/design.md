# Project Design and Methods
## Goals
Determine whether the compensation for various factors in Warframe not 
presented in Homestream 6's plots and can reveal trends not observable 
in the original data.

## Limitations and Assumptions
* Due to not having direct access to the real data, pixel approximations 
of the data were made based on pixel measurement of a full-screen 
1920x1080 monitor screenshot on the Twitch version of the stream. 
The video, at time of writing, is available 
[here](https://www.twitch.tv/videos/744879935). 
    * This leads to a loss in data granularity, especially for plots 
    with multiple frames sharing similar values; I doubt this will 
    greatly impact results, but worth noting nonetheless.
* Explicit data values are missing for all plots, so all values were 
measured as pixel-length-on-image using GIMP then scaled from 1 to 0 
using l2 normalization (read 
[this](https://limitlessdatascience.wordpress.com/2019/04/16/normalisation-l1-l2-norms/) 
for a rundown of the process). This scaling was also applied to other 
metrics to standardize them for direct comparison.
    * l2 normalization was chosen simply because it is standard, while
    also providing some compensation for outliers. The larger values it 
    often creates makes analysis slightly easier and less prone to 
    floating point rounding errors as well.
* Correlation between datasets was done using "Pearson's Correlation 
Coefficient", with the ability associated to the value being used as 
the label for each datapoint, falling back on Warframe name if the data 
does not relate to a given ability.
    * For example, the label for "bile cost of frame subsuming" is the 
    name of the Warframe, while "bile cost of imprinting ability" is the
    name of the Ability being imprinted.
    * The X axis is always sorted from greatest to least metric for all 
    plots, unless explicitly mentioned otherwise.
* Frame popularity was **NOT** accounted for, due to the period between
the last mention of it and now including a number of balance changes, 
new frames etc. The data is simply not valid in modern Warframe, and 
likely would have skewed the data.
* As of writing, data is still be collected on "average time to obtain 
full Warframe"; however, the following procedure is used to collect said 
data:
    * All measurements are made for the time the player must actively be
    farming for given frame under ideal circumstances (timers where a 
    player is simply waiting for daily standing/frame part building/
    new NW challenges etc. are ignored, under the assumption the player
    will simply do something else in the meantime)
    * For Warframe's dropping from missions, benefit of the doubt is 
    given and the best-of-five runs is used (this is to account for
    bad RNG creating exceptionally poor runs, or the fact I may be 
    using a less-than-optimal setup)
    * Unless otherwise mentioned, all runs were done in a pub squads
    (when available) or solo. This is presumed to be a middle ground 
    between pure solo players and tightly-coordinated squads. Runs 
    were run in October 2020, shortly after the Helminth system dropped
    but late enough that the player influx caused by the new update 
    had dwindled.
    * All missions were run using a kit appropriate to the mission, 
    while not min-maxing fully (we assumed most pub squads aiming for 
    parts for Helminth teams will be doing the same). I have all frames
    available to me, with their primed variants sans Titania and Inaros.
* *All data collected in this manner should be taken with a grain of
salt; the data is, at best, circumstantial, but unless DE releases more 
detailed data for the entire community, it is the best I can do given 
the time available.*
* This project is in no way affiliated with Digital Extremes or any of 
their affiliates; this is done solely for the sake of curiosity, and any 
interpretation of the results pertaining to said parties should be 
treated as speculative.