# AI Use Log 11/19/26

Tool: Google Gemini

Model: Gemini Chat

Version: Gemini 3.5 Flash

Prompt: "how to modify this code so that short-tongued insects and long tongued insects are grouped together to form 3 possible pollinator types: beetles, birds, and tonged-insects", "explain what each of these cells is doing and how it re-groups the categories"

What was changed before committing: i added a line of code from our original chunk for splitting groups that confirms no leakage occurred by looking through and checking the names of the plant species included in each of the subsets created

How correctness was verified: running the verification line of code and getting the text that prints no leakage has occured


# AI Use Log 11/16/26

Tool: Microsoft Copilot

Model: Copilot Auto

Version: bizchat.20261114.70.3

Prompt: A) "what are the groups i define for validation using groups = np.array with a multilabelbinarizer transformed dataset where microbes present for each different plant sample are binary and include pollinator type data" B) "can i use df["Plant species"] to define groups using groups = np.array instead of typing out each plant species in the dataset?"

C) "how to do grouped validation and a simple baseline using random forest threshold 0.50"

What was changed before committing: A, B) nothing, I used this prompt to confirm what I was already going to do and to better understand how to write the data using code from this website: https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GroupKFold.html 

C) this was used as a skeleton outline of the code we needed to do the grouped validation and simple baseline, i changed the random state value and used the website linked above along with this one (https://www.geeksforgeeks.org/machine-learning/random-forest-algorithm-in-machine-learning/) to understand what each parameter does. i typed the chunks of code needed in by hand and used tab to autofill with the object names i created in colab. i ran this, and then got errors from typos and mislabeled objects from when i was changing names as i typed the code by hand, so Gemini 3.5 Flash in Google Colab "cleaned" this

Output from Gemini 3.5 Flash corrections in Colab chat: 

Please explain this error:

The primary error occurs at simple_baseline[y_40.mean() >= 0.5] = 1. The variable y_40 (or y_test) contains string categorical labels (such as 'Beetle' and 'Birds'), which cannot be averaged using .mean().

Additionally, there are several other issues in this cell:

stratify=y_40: In the second train_test_split, stratify=y_40 is referenced before y_40 exists.
Missing Import: RandomForestClassifier is not imported.
Undefined Variables: rf_model is referenced instead of random_forest, and proba is used to calculate threshold predictions without being computed.
Variable Misspelling: fl is defined but f1 is appended to cv_scores.
GroupKFold issues: Using 43 splits on X_test with only 37 samples will fail since n_splits cannot exceed the number of samples.
Here is the corrected and fully functional code for cell Wz5jZC7tV6Y4:

The original error that occurred before the recent cell updates was caused by trying to compute the average of categorical labels directly:

TypeError: unsupported operand type(s) for +: 'str' and 'str' (or similar numeric-reduction errors) inside the expression y_40.mean() >= 0.5 because y contains string categories (such as 'Beetle', 'Birds', and 'Long-tongued insects').

Additionally, the following issues were resolved during the cleanup of cell Wz5jZC7tV6Y4:

Undefined Variables: y_40 was referenced in the stratify parameter before it was ever defined.
Import Error: RandomForestClassifier was being instantiated without being imported.
Cross-Validation Mismatch: Attempting 43 splits on GroupKFold on the validation/test sets failed because n_splits cannot exceed the number of unique groups (or samples) present in those subsets.
Typographical Error: The metric code calculated fl = f1_score(...) but appended f1 to the score tracker.
The code has since been corrected and executed successfully, yielding a baseline accuracy of 0.5676 and a Random Forest test set accuracy of 0.7568 (F1 score of 0.6018).

How correctness was verified: cross checked with the previously listed websites

# AI Use Log 11/15/2026 

Tool: Google Colab Gemini Chat

Model: Google Gemini 

Version: Gemini 3.5 Flash

Prompt: "how to perform class counts on dryad dataset?" "code to split multilabelbinarizer output into 60% training, 20% validation, 20% test"

What was changed before committing: added missing column names, read through code and changed object names to names we would recognize more easily as the elements of our dataset so that we understand what it is doing with the data better

How correctness was verified: command + F in Google Sheets dataset to confirm value occurances match with code output 

