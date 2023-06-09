# Growing Isotropic Neural Cellular Automata

Motivation is that neural cellular automata have inherent "weakness" in that they are not orientation invariant. If you grow a flower facing up, it can only grow upwards.

Their two ideas are rotation invariant training and using structured seeds to introduce asymmetry.

If you introduce multiple *unique* seeds that each correspond to a certain place on the image, then you're able to rotate those points and generate rotations. Their other idea is quite nice in that you make the loss rotation invariant by going into polar coordinates then use a FFT to find the minimum loss.

They also modify the loss to include an *auxillary loss* where you set arbitrary values (-0.5 and 0.5 in this case) which helps the model break symmetry. In the case of a heart, they find that using vertical halves as targets isn't enough, so they go and generate a ring with different target values. This does seem a little contrived and like a bit of a hack to get this particular thing to work.

Super cool thing they show that even though they think that async updates are important to breaking symmetry, the model is able to **escape** symmetrical hell by exploiting floating point non-associativity in the Laplacian filter. Interesting that by "growing" models that learn, we can learn something about the systems they're a part of. Like how models "reward hack" in video-games or find exploits, we shouldn't be surprised that unless airtight, models will find some hole to exploit.