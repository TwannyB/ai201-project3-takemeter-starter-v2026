# TakeMeter

> ### 👋 Start here
>
> **New to this repo? Read [RUNNING.md](RUNNING.md) first** — setup, the
> notebook, the baseline, and what to do when something breaks.
>
> Once `python test.py` passes:
>
> ```bash
> head -5 data/practice_labels.csv     # the shape your labels.csv needs
> ```
>
> Then open `takemeter.ipynb` **in this folder** — in VS Code, or with
> `jupyter notebook` if you prefer. Pick the kernel: the `.venv` inside this
> project. Run section 1, which reports the hardware you'll be training on.
> Everything else waits until you have data.
>
> Nothing to upload, nothing to connect, no accounts and no keys. The notebook
> runs on your machine and writes next to your code.
>
> **The rest of this file is your submission.** Fill it in as you go.

---

<!-- ─────────────────────────────────────────────────────────────────────────
     HOW TO USE THIS FILE

     Unit 5 asks for the first five sections. Unit 6 adds the five below them.

     Everything is pasted as TEXT. No screenshots, no images.

     ⚠️ The confusion matrix especially. The notebook prints one as a markdown
     table, ready to copy. A screenshot of a matrix earns nothing. Paste the
     table.
     ───────────────────────────────────────────────────────────────────────── -->

<!-- ═══════════════════════ UNIT 5 — THE BUILD ═══════════════════════ -->

## What This Does

<!-- Your community, and what your classifier sorts posts into. Three or four
     sentences. -->
The community I chose to select posts from is the J.Cole subreddit community. The classifier sorts the posts into the categories: humorous, concert_question, news_update, and opinion. I chose the four categories because I felt as though most of the posts that I viewed could be sorted into those four categories.


---

## Label Taxonomy

<!-- Each label: a one-sentence definition and two real examples from your
     reading. Then your decision rule for the hardest boundary.

     The decision rule is worth a point on its own and it's the thing most
     people leave out. Every taxonomy has a hardest boundary. Name yours. -->

### `humorous`

**Definition:**
Mainly intended as a joke, meme, or sarcastic remark about J. Cole or related topics. 
Use when the joke is the main point; a casual joke attached to a serious request does not 
automatically make it humorous.

**Example 1:**
>"J Cole seen sitting down and drinking a can at his Dallas concert. How does this effect your love for this “humble rapper"

**Example 2:**
>"I met J Cole, my life is now inspired by humbleness.

I walked into the KFC, to see J Cole sharing his food with everyone. He didn't even eat it himself. When I asked 
him why he said "eating food isn't humble enough for me." I pulled out my phone and asked if we could take a 
picture. J Cole gave me a puzzled look and tapped my phone screen, "What is this thing you hold in your hand?" 
"This is a phone, are you stupid?" I said to J Cole, He tilted his head "I am too humble to know what a phone is." 
He then climbs up the roof of KFC and pulls out his blanket, Cole lays down and attempts to fall asleep. "Don't 
you have to go home, Cole?" I ask before he looks at me confused, "What's a home? Sounds a bit snobby and 
materialistic to me! My blanket and my moldy KFC roof is all I need!""

### `concert_question`

**Definition:**
Asks for practical information about attending a J. Cole concert, such as tickets, venues, 
schedules, seating, or entry rules.Includes requests for advice about attendance decisions. 
Excludes rhetorical questions that mainly express praise or frustration.

**Example 1:**
>" Are the tour towels for everyone attending the tour in Europe too?
After seeing posts about the white towels handed out at the US concerts, I was wondering if these are 
just for VIP tickets or for everyone and if these are also handed out at European concerts?"

**Example 2:**
>"Timing J. Cole Antwerp
I'm planning to arrive around 7:30, an hour after the doors opened and half an hour before the opening/
dreamville radio/... What standing places can I expect? At the moment I'm hoping I'll still have a good 
spot in the middle of the crowd, no too far to the back but also not very far in the front of course."

### `opinion`

**Definition:**
Expresses a personal judgment about an artist, song, album, performance, or ranking. 

**Example 1:**
>"Finally understood this song ... J. Cole has been my favorite artist for a couple years now, but I never really understood Love Yourz which is one of his most praised songs. I obviously knew what it was saying but only when I was thinking late at night about why we're even here, about what my actions actually achieve, did I really see what he was saying.Its about understanding that life is about living, not just about grinding and thinking about how to reach that next level. If you don't appreciate the beautiful things that life has to offer, then you get caught up in all of the harsh realities instead. What an amazing song."

**Example 2:**
>"Bronx Zoo Freestyle was his best this year The aggression after the build up was something I really wished on The fall off. He's been so technical this decade that hearing him keeping it while sounding so hungry. It's prolly among his top 3 verse ever for me along with Jermaine's interlude and a plate of collard greens"

### `news_update`

**Definition:**
Primarily shares or seeks verification of concrete updates about J. Cole, 
including releases, tours, collaborations, or appearances.
**Example 1:**
>"Kyle Kuzma from the lakers rocking a new J. Cole x Puma collab shoe thats currently unreleased."

**Example 2:**
>"Dreamville Fest Lineup Change: Chris Brown replaced with 50 Cent"


### The hardest boundary

**Which two labels:** humorous and opinion

**The decision rule I used every time:**
Choose humorous when the main purpose is a joke or exaggerated mock judgment; choose opinion when the main purpose is a sincere evaluation. If the text alone doesn’t establish the difference, exclude it.



---

## The Dataset

<!-- Where you collected from, how you labelled, your counts, and three hard
     cases. -->

**Where the posts came from:** The r/Jcole subreddit on Reddit.com

**How I labelled them:** I labelled each one manually except for ones I was unsure on, when I used AI to help me classify. I then had AI verify my selections for the ones I classified cold.


**Counts per label:**

| Label | Count | Share |
|humorous|28|14%|
|concert_question|49|24.5%|
|opinion|91|45.5%|
|news_update|32|16%|
| **Total** |200| 100% |

**Three hard cases**

<!-- Any post that made you pause: what it was, which two labels it could have
     been, and what you chose. These are worth more than the easy 190. -->

**1.**
> *The post:*
>J.Cole concert Eu I have been thinking of going to four other countries Hamburg,Denmark,Sweden and Norway to see J.cole again after seeing him in Switzerland.he was amazing and I became a super fan right after and it’s allegedly his last tour and i am really thinking of seeing him again…well i get to see other european countries too but the concert is like the anchor lol.. What do you all think ? is that dumb ? I know he’s going to perform the same set list but it’s J.cole Helppppp
> *Could have been:* 
>opinion or concert_question
> *I chose, because:* concert_question because it seeks advice about traveling to attend more concerts, while also praising the performance. The writer would more likely want a response to their question over a response to their opinion.

**2.**
> *The post:* 
>Jcole makes newspapers for people that listen to music

> *Could have been:* 
> humorous or opinion

> *I chose, because:* Humorous, because the metaphor of newspapers is a joke about the "old school" reputation his fans are given.

**3.**
> *The post:*
>The Dreamers I’ve been seeing some news online about Dreamville kinda falling apart with jid and ari Lennox but id say ari isn’t that big of a loss her background vocals will definitely be missed especially on 4yeo and 2014 FHD they were essential but I feel like jid should be the focus on keeping because he’s so fucking good I don’t think anybody here regularly listens to ari Lennox but everybody here listens to JID for sure I wish cole would LET HIM RELEASE THE METRO TAPE if he’s the one stopping it since I think that’s the main reason he’s tryna leave also guys why’s j cole stopping dreamville fests?

> *Could have been:*
>opinion or news_update
> *I chose, because:*
Opinion, because although a few Dreamville members and Dreamville's their relationships are mentioned, the author is mainly evaluating artists and expressing their wishes.
---

## The Training Run

<!-- Your starting model, your settings, and anything you changed and why. -->

**Base model:** "distilbert-base-uncased"

**Settings:** <!-- epochs, learning rate, batch size, seed -->
EPOCHS = 3
LEARNING_RATE = 2e-5
BATCH_SIZE = 16

**Anything I changed from the defaults, and why:**
I didn't make any changes.

**Split sizes:** 
<!-- train / val / test, and per-label counts in the test
split. If a label had fewer than about 8 in test, say so — it explains a lot
of next unit's variance. -->

train:139  ·  val:31  ·  test:30
humorous, concert_question, and news_update all had fewer than 8 examples in the test split.


---

## How I Used AI

<!-- Two specific moments — what you asked, what came back, what you changed.

     ⚠️ Plus disclosure of any pre-labelling. If you had a model pre-label a
     batch and then read and corrected every one, say that. It's an allowed
     workflow and disclosing it costs you nothing. Not disclosing it is the
     problem. -->

**Moment 1**

- *What I asked for:* I asked ChatGPT to help me better define my labels by giving it my current definitions.
- *What came back:* It gave me back improved definitions that made it easier to classify posts in the future.
- *What I changed:* I kept its adjustments, but looked over example posts that were close to boundaries and examined them according to the new definitions to make sure the definitions hold up.

**Moment 2**

- *What I asked for:* I asked ChatGPT to help me classify obscure posts.
- *What came back:* ChatGPT recommended categories and gave reasoning. 
- *What I changed:* I reviewed the classifications and checked them by the definitions we created before implementing them into labels.csv.

**Pre-labelling disclosure:**
No batch was pre-labelled by a model. 13 of 200 posts, the ambiguous ones, were labelled with ChatGPT's help (see Moment 2): it suggested a category and its reasoning, and I checked each one against my label definitions before writing the final label. Those rows are marked AI-assisted label review, checked in the note column. The 20 cold examples were labelled with no AI help.

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure | Baseline | Trained | Difference |
|---|---|---|---|
| Overall accuracy | 0.533 | 0.467 | -0.067 |
| Macro F1 | 0.354 | 0.159 | -0.195 |
| F1 — `concert_question` | 0.250 | 0.000 | -0.250 |
| F1 — `humorous` | 0.000 | 0.000 | +0.000 |
| F1 — `news_update` | 0.500 | 0.000 | -0.500 |
| F1 — `opinion` | 0.667 | 0.636 | -0.030 |

**What I predicted before I looked:**
I think my trained model will have a better overall accuracy, and also better precision


**What the gap actually means:**
My trained model performed worse, meaning that my fine tuning failed to improve, but worsened the performance of the model.

---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1. Overall accuracy | ≥0.80 | 0.46 | 0.46 | 0.43 | MISSED |
| 2. F1 score for humorous and others| ≥0.60(humorous), ≥0.80(others) | 0.63(opinion), 0(humorous), 0(concert_q), 0(news) | 0.63(opinion), 0(humorous), 0(concert_q), 0(news) | 0.60(opinion), 0(humorous), 0(concert_q), 0(news) | MISSED |
| 3. Largest category not too big| 0.70<= | 0.46 | 0.46 | 0.46 | MET |
| 4. Sample of 10, classifications agree with another person | 7 | 8 | 8 | 9 | MET |
| 5. Boundary between concert_question and opinion, correct classifications out of 10 | 7 | 4 | 3 | 3 | MISSED |

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

| true \ predicted | opinion | humorous | concert_question | news_update |
|---|---|---|---|---|
| **opinion** | 14 | 0 | 0 | 0 |
| **humorous** | 4 | 0 | 0 | 0 |
| **concert_question** | 7 | 0 | 0 | 0 |
| **news_update** | 5 | 0 | 0 | 0 |

**My biggest off-diagonal number, and what it means:**
<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->

The model confused 7 real `concert_question` posts as opinion and 0 were confused the other way around.
This could mean that my training data was inconsistently labelled in some way, but the model can correctly recognize
`opinion` posts as opinion. 




---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 |Overall accuracy | ≥0.80 | MISSED |  |
| 2 |F1 score for humorous and others| ≥0.60(humorous), ≥0.80(others) | MISSED |  |
| 3 |Largest category not too big| 0.70<= | MET |  |
| 4 |Sample of 10, classifications agree with another person | 7 | MET |  |
| 5 |Boundary between concert_question and opinion, correct classifications out of 10 | 7 | MISSED |  |

**Diagnoses**

<!-- For each miss: the cause, and how you know. The four common causes are:
     too few examples for a label, a boundary you applied inconsistently, a
     genuinely hard label pair, and a task the model can't reach from this
     much data.

     ⚠️ Use your agreement report as evidence. It is the only instrument you
     have that can tell a LABELLING problem from a MODEL problem, and this
     section is graded on whether you used it that way. -->



---

## Agreement Report

<!-- Your rate against the staff set, and every disagreement adjudicated.

     Remember you labelled these 30 under the STAFF taxonomy in
     data/staff_taxonomy.md, not your own — so every argument below is made
     from those definitions and those decision rules. -->

**Agreement rate:** _23_ / 30 = _77_%

<!-- Nobody grades this number. A 60% who argues every disagreement from the
     stated rules beats a 95% who wrote "staff was right" nine times. Several
     of the 30 were chosen because they're genuinely ambiguous — you should be
     winning some of these. -->

**Disagreements**

<!-- Three lines each: the post, both labels, and who you think is right and
     why — grounded in the staff definitions you were both applying.

     Then sort each into one of three piles:
       (a) the rule covered it and I applied it loosely → a consistency problem
       (b) the rule genuinely doesn't say               → a gap in the definitions
       (c) the rule is ambiguous here and my reading is defensible → argue it.
           This is a legitimate win.

     Pile (a) is the one that matters most for your diagnosis: if you applied a
     written rule two different ways on 30 posts, that is direct evidence about
     what you did across your own 200. -->

**1.**
> *The post:*
>The club championship scoring changed in 2019 from top-6 to top-10. S…
> *Staff said / I said:*
>The staff said `analysis`, I said `hot_take`.
> *My call, and why:*
>I agree with the staff's post and think I applied the rule loosely although it covered it, because I wasn't sure if the last sentence in the post was a clear conclusion to come to or an opinion. Looking back, I understand that top 10 means it's easier for a B team to score if it has more people, so the scoring supports the conclusion and the post isn't a hot take and the rule covered the post, so I was wrong.
> *Which pile:* a

**2.**
> *The post:*
>Everyone blames the hill at 18 miles. I split the field into people w…
> *Staff said / I said:*
>Staff said `analysis`, I said `hot_take`.
> *My call, and why:*
>I agree with the staff's post because the writer supported their claim by comparing the slowdown of the two groups, which is analysis. I was confused by the last sentence's confident claim, which sounded like a controversial opinion since I didn't understand the reasoning. Whether I 
understood the reasoning or not, the evidence was relevant to the conclusion, making it analysis, so I applied the rule loosely..
> *Which pile:* a

**3.**
> *The post:*
>Carbon plates aren't the whole story. My times dropped 2% in the shoe…
> *Staff said / I said:*
>Staff said `analysis`, I said `reaction`.
> *My call, and why:*
>I think I loosely applied the rule. The post mentioned the writer's personal experience, so I thought it was a reaction, but the facts being present outrank the experience, even if the post was about a recent occurence, so the staff's classification is better supported.
> *Which pile:* a

**4.**
> *The post:*
>Checked the entry lists. 41% of this year's field have never run the …
> *Staff said / I said:*
>Staff said `analysis`, I said `hot_take`
> *My call, and why:* It was unclear whether the facts stated were relevant to the conclusion made, so I wasn't sure if the facts were load bearing, which would make it analysis according to the rules. However, I do think the staff was correct again because of fourth rule that states whatever the post spends more time on is the classification, which in this case is analysis. Therefore, I applied the rules loosely here.
> *Which pile:* a

**5.**
> *The post:*
>Ran the same loop in 4C and in 24C within a fortnight, same effort by…
> *Staff said / I said:*
>Staff said `analysis`, I said `reaction`
> *My call, and why:*
> I think I loosely applied the rules. I thought that because the post involved the writer's experience, it was a reaction to their change in time. However, the rule states that a post, even if about a recent experience is still analysis if it argues from a checkable fact, so the staff is correct here.
> *Which pile:* a

**6.**
> *The post:*
>Went back through the club results going back to 2012. Every single y…
> *Staff said / I said:*
>Staff said `analysis`, I said `hot_take`
> *My call, and why:*
>I loosely applied the rules. I believed that because the post had a last sentence that gave a conclusion about what was going on, it could have been a hot take. However, the facts given are relevant and "load bearing", so analysis is the classification the rule actually supports.
> *Which pile:* a

**7.**
> *The post:*
> Three of us ran the same session on the same day, different shoes, wi…
> *Staff said / I said:*
>Staff said `analysis`, I said `reaction`
> *My call, and why:*
>I think I again loosely applied the rules, mostly because I don't agree with the rules. By rule 3, the post is analysis despite the post possibly being about a recent event or a person's experience because it contains a checkable fact. I labeled it reaction because the writer's experience seemed more prominent in the post to me.
> *Which pile:* a


**What the pattern in my disagreements tells me:**
I often mistook analysis posts for other post classes, mainly because I didn't apply rules well, but instead went with gut feelings and my own logic about what I thought was most important in the post.


---

## The Improvement

**What I changed:**

**Which diagnosis pointed at it:**

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

**Did it help, and how do I know:**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->



---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->



**The gap between what I meant my labels to capture and what the model
learned:**
<!-- Two sentences. Your confusion matrix is the evidence. -->



<!-- ═════════════════════════════════════════════════════════════════════

     SUBMISSION CHECKLIST — unit 5

       [ ] criteria.md has five numbered criteria, each naming a NUMBER
       [ ] Each has a reason underneath tied to your data or taxonomy
       [ ] labels.csv: at least 150 rows, text/label/note, ONE file not split
       [ ] No label above 70%
       [ ] All five unit 5 sections have real content
       [ ] Label Taxonomy includes the decision rule for your hardest boundary
       [ ] The Dataset includes three hard cases
       [ ] results.json and test_split.csv committed (the notebook does this)
       [ ] At least four new commits
       [ ] Repository URL submitted — WRITE IT DOWN

     SUBMISSION CHECKLIST — unit 6

       [ ] Baseline vs. Trained table, with your prediction written beforehand
       [ ] Run Log — Before, five criteria across three seeds
       [ ] Confusion matrix TYPED AS A MARKDOWN TABLE
       [ ] A verdict on every criterion
       [ ] A diagnosis for every miss, using the agreement report as evidence
       [ ] Agreement Report with every disagreement adjudicated
       [ ] One improvement, with Run Log — After
       [ ] What's Still Broken
       [ ] results_three_seeds_before.json, results_three_seeds_after.json,
           baseline_results.json and
           agreement_results.json committed
       [ ] At least four new commits
       [ ] The SAME repository URL as last unit

     Do not delete and recreate this repository.
     ═════════════════════════════════════════════════════════════════════ -->

---

📖 **How to run this project: [RUNNING.md](RUNNING.md)**
