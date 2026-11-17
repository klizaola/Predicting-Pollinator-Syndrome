# AI Use Log 11/16/26

Tool: Microsoft Copilot

Model: Copilot Auto

Version: bizchat.20261114.70.3

Prompt: A) "what are the groups i define for validation using groups = np.array with a multilabelbinarizer transformed dataset where microbes present for each different plant sample are binary and include pollinator type data" B) "can i use df["Plant species"] to define groups using groups = np.array instead of typing out each plant species in the dataset?"

C) "how to do grouped validation and a simple baseline using random forest threshold 0.50"

What was changed before committing: A, B) nothing, I used this prompt to confirm what I was already going to do and to better understand how to write the data using code from this website: https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GroupKFold.html 

C) this was used as a skeleton outline of the code we needed to do the grouped validation and simple baseline, i changed the random state value and used the website linked above along with this one (https://www.geeksforgeeks.org/machine-learning/random-forest-algorithm-in-machine-learning/) to understand what each parameter does. i typed the chunks of code needed in by hand and used tab to autofill with the object names i created in colab

How correctness was verified: cross checked with the previously listed websites

# AI Use Log 11/15/2026 

Tool: Google Colab Gemini Chat

Model: Google Gemini 

Version: Gemini 3.5 Flash

Prompt: "how to perform class counts on dryad dataset?" "code to split multilabelbinarizer output into 60% training, 20% validation, 20% test"

What was changed before committing: added missing column names, read through code and changed object names to names we would recognize more easily as the elements of our dataset so that we understand what it is doing with the data better

How correctness was verified: command + F in Google Sheets dataset to confirm value occurances match with code output 

