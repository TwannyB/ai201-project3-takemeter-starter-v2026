# Acceptance criteria — TakeMeter

Five criteria that say what "working" means for this classifier, written in
unit 5 **before** anything was trained.

**All five are yours this time.** None are given. You've had two projects of
practice.

An acceptance criterion names a number. *"The model is accurate"* is an
opinion. *"Every label has an F1 of at least 0.60 on the held-out set"* is a
criterion.

Under each, write a sentence or two on **why that number**. A reason that says
something about your data or your taxonomy earns credit — *"I picked 0.60 F1
for `reaction` because it's my smallest label and I only have about 50
examples of it"*. A reason that could be attached to any project does not.

> Missing your own targets next unit costs you nothing. Setting a target so
> easy you can't miss it does.

---

## Pick numbers you can defend

Not numbers that sound impressive. Three labels means a coin-flip guesser gets
about 33%, so a target of 0.40 is barely a target. Your number should sit
somewhere you'd honestly call useful.

**Cover at least three of these five areas.** They're here as prompts, not as a
form to fill in — a criterion that fits none of them is fine if it names a
number.

| Area | A question it could answer |
|---|---|
| Overall accuracy | How often does it need to be right to be worth using? |
| Per-label performance | Is one label allowed to be much worse than the others? |
| Balance | How lopsided can your label counts get before it's a problem? |
| Consistency | If someone else labelled the same posts, how often should you agree? |
| Confidence | Should a confident prediction be right more often than an unsure one? |

Two things worth knowing before you pick numbers, because both will affect
whether you hit them:

- **Your smallest label will have the jumpiest score.** If a label has 50
  examples, about 8 land in the test split. An F1 computed on 8 examples moves
  a lot between seeds. A target for that label should be looser than one for
  your biggest label, and saying so is a good reason.
- **Unit 6 tests across three seeds, and the target has to hold across all
  three.** A target of 0.65 against results of 0.71, 0.62, 0.68 is a **miss**.
  Pick with that in mind — it is stricter than it first sounds.

---

## 1.
The model's accuracy is at least 80% overall.



**Why this target:**
I want no more than about one in five predictions to be wrong, anything lower than 80% would would be an unsuccessfully trained model.



---

## 2.
The F1 score for humorous posts in the held out set is at least 0.6, and the F1 score for the rest of the categories are 0.8 or higher for the held out set. 

**Why this target:**
Posts in the category of humorous that don't include a picture or that can still be identified as humoruous without a picture are rare on Reddit, so it will be tougher for the model to accurately classify them. The rest of the post categories, however, are more common, so they should have more training examples and clearer textual signals.



---

## 3.

The largest category in the dataset may not be more than 70% of the dataset. 



**Why this target:**
I chose for the threshold for the most common classification of the data to 70% because any higher would risk preventing the model from successfully predicting other classifications. It also abides with the assignment's recommended maximum.



---

## 4.

On a sample of 10 posts, another person and I will independently assign labels using the same definitions and agree on at least 7 of the posts before discussing disagreements.

**Why this target:**
I'd accept disagreement on three out of every ten posts because some boundaries like opinion and humor or concert question and opinion can be obscure, but they shouldn't appear more than 3 times in a set of 10 since they aren't common.




---

## 5.
On a set of 10 held-out boundary posts between concert_question and opinion, the model will correctly classify at least 7.

**Why this target:**
I know there's already some difficulty having another model properly classify these myself, and I chose 7 out of 10 because it the goal is for the model to handle the most difficult cases more than half of the time.


---

<!-- ─────────────────────────────────────────────────────────────────────────
     UNIT 6 — read this before you change anything above.

     If a criterion turns out to be BROKEN rather than merely unmet, you can
     revise it, and that earns credit. But never delete or edit the original
     line. Add the revision underneath, like this:

         ## 2. Every label performs acceptably

         The model performs well on all labels.

         **Why this target:** ...

         > **Revised in unit 6:** Every label has an F1 of at least 0.60 on
         > the held-out set.
         >
         > **Why revised:** "performs well" gave me nothing to check. I
         > couldn't produce a verdict from it at all.

     That's a revision because the criterion couldn't be MEASURED.

     Lowering a target because you missed it is not a revision, and it costs
     you the point:

         ✗ "Overall accuracy of at least 0.65" → "at least 0.55", because
            0.65 turned out to be optimistic for 200 examples.

     A number you missed stays where it is, gets diagnosed, and gets a fix
     attempted. That's where the points are.
     ───────────────────────────────────────────────────────────────────────── -->
