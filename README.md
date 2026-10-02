Kensu

An attempt at detecting LLM hallucinations from the model's own behaviour: token probabilities, entropy, and consistency across repeated runs. Built by me and my brother.

Status: paused prototype (v0-prototype)

Tested only on simulated data. There are no real results. The full pipeline runs end to end (collection, labelling, features, training, evaluation), but every number it produces comes from a dummy data generator, so none of them are findings.

I've stopped working on it. It's too big for the time I have, and I'd design it differently now. I'm not rebuilding it or swapping in a premade dataset to keep it going.

Known problems
The dummy data generator builds the answer into the signals.
Fake-citation questions are always labelled hallucinated, even when the model correctly refuses.
The label comes from run 1 only, but the features use all five runs.
The baselines in evaluate.py aren't comparable to the Random Forest.
The "hallucination probability" is uncalibrated because of class_weight="balanced".
What I learned

Simulated data can make a pipeline look finished while hiding the hard part. Labels and features must come from the same place, baselines must be evaluated like the model, and next time I'd start with one domain and real data from day one.