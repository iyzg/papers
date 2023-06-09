# Tracking floor eggs with machine vision in cage-free hen houses

Although free-range chickens provide healthier eggs and are more humane, they are also more prone to laying "floor eggs" (eggs on the foraging floor) which get contaminated and pecked at. This paper aimed to try and automate the identification aspect of the pipeline that would tell if an egg was on the floor.

General gist is that they finetune a Yolo-v5 & v7 and see how well they perform with findings that the largest model (v5x) is the most performant.