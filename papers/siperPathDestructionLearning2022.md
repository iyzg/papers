# Path of Destruction: Learning an Iterative Level Generator Using a Small Dataset

The basic idea is that you can generate game levels by *fixing broken ones* using a *NCA* that is trained to repair levels! If you do that, then you're able to create entirely new levels given random ones. Key note is that their method is able to generalize off a *small focal field* and a *small dataset*. If you're able to learn the rules from a small dataset, then you should be able to generalize to create ~infinite new levels is the hope.

Like curriciulum learning or diffusion models, they start from a regular level and slowly degrade it with a **path of destruction** to create a dataset that ranges from normal level to random level. Hopefully if done correctly, you'll be able to learn how to repair levels and then generate new levels.

The thing is, this isn't just a diffusion model where you're iteratively adding noise and trying to learn a distribution. In this, you're destroying tiles one by one and hoping the model can learn the subsequent repair function.

Path of destruction loop:
1. Start with noise and pick the closest handmade level in terms of Hamming Distance
2. Pick a random tile from the handmade level and turn it to corresponding index from noise
3. Continue until the two levels are the same and you have a training trajectory

Creation loop:
1. Start with noise distribution from PoD
2. Select a tile and repair it with NN
3. Keep going until you reach threshold or it is playable

Interesting notes here that the larger the observation size (think neighborhood size), the less unique the levels get! The model isn't able to learn how to uniquely model local interactions anymore, but there are more *playable, but not unique* levels. For goal size, the smaller the reference set, the more *playable* but less *unique* it was. The lesson here seems to be yet again you want large dataset, but you also want to have constrained windows! Having perfect information can be seen as a flaw almost to the creativity/chaotic nature of the system.

> Q: How do you decide on a neighborhood that is *right* for a problem? Perhaps if you reframed it as a graph problem then you may be able to figure this out? Adaptive graphs where nodes can change neighborhoods? This idea doesn't really work out.

Note that Hamming Distance is actually a *poor measure* of level diversity. Even if a level is only one pixel different, the A* solution might be *extremely different*. It's interesting that one should look at phenotypic diversity *instead of* genotypic diversity to create diverse solutions.

I also really enjoy their discussion on how destroying a valid dataset in a lot of random different ways can be seen as a form of data augmentation almost. 