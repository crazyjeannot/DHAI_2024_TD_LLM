# DHAI_2024_TD_LLM - Group Project 2:
This repository contains the main materials for the PSL-Week "Digital Humanities meets Artificial Intelligence" project on LLMs for fiction:

Measuring predictability and surprise in adventure and police fiction: an approach to automatic tagging of literary scenes

Computational literary studies (CLS) are a branch of digital humanities that specialises in the automatisation of literary analysis in the aim of processing large corpora of text that are out of the scope of human close reading capacities. This can be used in order to identify trends, extract information, classify works, find entities and many other applications to explore vast amounts of information.

One of the main interests of CLS is the study of the internal structure of literary works, which is often done by searching for specific traits in fragments of texts, and then aggregating these individual results in a more global analysis in a second time. It is less common to work with complete texts all at once, because the length of most literary documents can easily surpass the window of context of algorithms and models.

In this project we will be looking at the capabilities of very recent Large Language Models (LLM) to predict some predefined tags related to literary genre in chunks of texts. Our goal will be to create a pipeline that correctly tags scenes in these excerpts so we can discuss about the structural difference of specimens of both adventure and police fiction.

As background for this task, we can point to Ted Underwood's research on fiction, which had led him to explore structural problems such as narrative arcs, generic classification, and, more recently, the use of LLM in literary analysis. We can specifically to the post called "Can language models predict the next twist in a story?" (https://tedunderwood.com/2024/01/05/can-language-models-predict-the-next-twist-in-a-story/). This entry in Underwood's blog shows an experiment asking a generative LLM to continue fragments of stories in order not only to understand the capabilities of the model, but also to try to represent uncertainty and surprise, two notions linked to the effect of suspense and other phenomena related to the reception of literature.

Many open questions will guide our investigation: How effective are language models in predicting genre tags from a limited amount of information? How is it possible to capture structural differences between adventure and police novels through the analysis of excerpts? How well can generative LLM infer the plot of fiction stories? How can we design systems to work effectively with long literary texts, such as novels?

With the purpose of avoiding copyright issues, and also following the line of our specific research interests, we will limit our study to literature published before the XXth century. We will take advantage of a selection of works of the corpus Chapitres () Three different corpora are capital for our research:

1. Detective fiction

1855 Barbara, Charles. L'assassinat du pont rouge.
1866 Gaboriau, Emile. L'affaire Lerouge.
1876 Boisgobey, Fortune du. L'Omnibus du diable.
1887 Pont-Jest, Rene de. Le Cas du Docteur Plemen.
1895 Lermina, Jules. L'enigme.

2. Adventure fiction

1857 Aimard, Gustave. Les trappeurs de l'Arkansas.
1863 Gautier, Theophile. Le capitaine Fracasse.
1870 Verne, Jules. Vingt mille lieues sous les mers.
1882 Aimard, Gustave. Les bandits de l Arizona.
1893 Feval, Paul (fils). Les suites de Lagardère 1 : la jeunesse du bossu.

3. General fiction of XIXth century

Four different models will be used in our experiments. As base mode, we chose mistralai/Mistral 7B-v0.1 because of its good performance and its capability to be run and fine-tuned with little GPU power. We will name our four models the following:

-Mistral-7B-v0.1 (base model)
-M-Adventure
-M-Detective
-M-19

The base model will give us a ground truth on the one-shot capacities of the model applied to our task. We will then perform three different fine-tunings on Mistral-7B-v0.1, in order to compare the outputs in the hope that models trained in literature that is similar to the one the experiments focus on will accomplish the task better than general instruction-following models.
