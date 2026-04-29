# Summary

A treebank of learner Swedish based on SweLL, the Swedish Learner Language corpus.

# Introduction
UD_Swedish-SweLL is a parallel learner treebank based on [SweLL](https://spraakbanken.gu.se/en/resources/swell), the Swedish Learner Language corpus.

More specifically, the treebank currently features 643 sentences from [SweLL-gold](https://spraakbanken.gu.se/en/resources/swell-gold), a corpus of essays written by adult learners of Swedish as a second language (L2):
  - a test set consisting of 509 randomly selected sentences
  - 134 sentences auhtored by French speakers (added in v2.18)

All essays in SweLL-gold are manually pseudonymized, error-labelled and _normalized_, i.e. accompanied by a correction hypothesis.
Error labels are available in the MISC field.
While the current UD release only includes original learner sentences, such corrections are available in the [`not-to-release`](not-to-release/sv_swell-ud-test-trg.conllu) folder of this repository. 

# Annotation
Each sentence-correction pair was pre-annotated with UDPipe 2 using the `swedish-talbanken-ud-2.15-241121` model. 
The resulting annotations underwent extensive manual post-correction.
Each pair was edited by two annotators, who are themselves L2 Swedish speakers and worked in parallel, meeting periodically to resolve disagreements. 
In the case of the 134 sentences written by French speakers, one of the annotators has French as her L1.

In particular:

- __lemmas, UPOS tags and dependencies__ were checked systematically
- __morphological features__ were only checked for tokens marked as learner errors in the source corpus and/or whose automatic lemmatization, POS tagging and/or dependency annotation were found to be incorrect
- SweLL-gold __error labels__, documented [here](https://gupea.ub.gu.se/bitstream/handle/2077/69434/gupea_2077_69434_1.pdf?sequence=1&isAllowed=y), are included in the MISC column and were used to automatically assign the `Typo=Yes` feature to tokens presenting orthography errors.

The general annotation principles for the annotation of interlanguage phenomena are as follows:

- __token-level annotation__ (lemmatization, POS tagging and morphological analysis) should be __purely descriptive__ of the observed word forms__ (also referred to as _literal_)
- __dependency annotation__ should also be __as descriptive of the observed language use as possible, but grounded in the correction hypothesis__ of the sentence whenever different interpretations of the learner's intended meaning would lead to different analyses. This is to ensure comparability between learner productions and their corrections
- in general, __annotation__ should be __aware of transfer phenomena__.


For a more comprehensive discussion of these principles, see [_Annotating Second Language in Universal Dependencies: a Review of Current Practices and Directions for Harmonized Guidelines_](https://aclanthology.org/2025.udw-1.17/) (Masciolini et al., UDW-SyntaxFest 2025), as well as the annotation guidelines for UD_Swedish-SweLL, available in the [`not-to-release`](not-to-release/guidelines.md) folder. 

On rare occasions (7 tokens), these principles clash with current UD validation rules. 
When this was the case, annotation was adjusted to comply with the general guidelines and the annotator's preferred analysis was moved to the MISC column under the key `IntendedXXX` (at the moment, only `IntendedDeprel` is attested).
This is, however, a temporary workaround pending a community discussion.

# Metadata
SweLL-gold comes with rich learner metadata that cannot be redistributed in full due to licensing restrictions.
We currently include:

- `approximate_level`: `Nybörjare` (beginner), `Fortsättning` (intermediate) or `Avancerad` (advanced). In the future, these labels may be replaced with CEFR levels
- `iso_l1`: the first language(s) of the author of the essay
- `iso_writing_language`: the language in which the author of the essay has the highest written proficiency
- `sent_id`: the sentence ID, whose format is `org-N-X` for original learner productions and `trg-N-X` for the corresponding correction hypotheses (`N` is a sequential ID, `X` specifies the group the sentences belongs to for annotation purposes, currently `test` or `fr`)
- `split`: the split the text belongs to (`train`, `dev` or `test`) for parsing purposes
- `text`: the full text of the sentence (pre-tokenized)

# Acknowledgments
The manual annotation work has been carried out by Arianna Masciolini, Aleksandrs Berdicevskis, Maria Irena Szawerna, and Caroline Grand-Clement with the support of the creators of the source corpus.
In particular, we want to thank Elena Volodina for her participation in the initial annotation experiments and Lisa Rudebeck for her clarifications about the original error annotations.

This work is funded by the Swedish national research infrastructure Språkbanken, jointly financially supported by the Swedish Research Council (2025–2028; grant 2023-00161) and the 10 participating partner institutions.
It received further support by the CA21167 COST action [UniDive -- Universality, diversity and idiosyncrasy in language technology](https://unidive.lisn.upsaclay.fr/).

# Contributing
If you spot any annotation errors or inconsistencies, please open an issue in this repository.
For legal reason, however, the annotation work is carried out in a private repository where sentences are stored with all learner metadata.
If you want to get involved, you are much welcome get in touch with the treebank's maintainer at arianna.masciolini@gu.se.

# References
A paper describing UD_Swedish-SweLL in detail is currently under review.
Meanwhile, if you use the treebank in you work, you are encouraged to cite the following related papers:

```bibtex
@article{swell,
  title     = {{SweLL} with pride: How to put a learner corpus to good use},
  author    = {Volodina, Elena and Masciolini, Arianna and Megyesi, Beáta and Prentice, Julia and Rudebeck, Lisa and Sundberg, Gunlög and Wirén, Mats},
  year      = 2025,
  journal   = {Huminfra handbook: Empowering digital and experimental humanities},
  publisher = {University of Tartu Library},
  volume    = {},
  pages     = {},
  url       = {https://doi.org/10.58009/aere-perennius0178},
}

@inproceedings{ud4l2-harmonization,
  title     = {Annotating Second Language in {U}niversal {D}ependencies: a Review of Current Practices and Directions for Harmonized Guidelines},
  author    = {Masciolini, Arianna and Berdicevskis, Aleksandrs and Szawerna, Maria Irena and Volodina, Elena},
  editor    = {Bomma, Gosse and {\c{C}}{\"o}ltekin, {\c{C}}a{\u{g}}r{\i}},
  booktitle = {Proceedings of the Eighth Workshop on Universal Dependencies (UDW, SyntaxFest 2025)},
  month     = {aug},
  year      = {2025},
  address   = {Ljubljana, Slovenia},
  publisher = {Association for Computational Linguistics},
  url       = {https://aclanthology.org/2025.udw-1.17/},
  pages     = {153--163},
  isbn      = {979-8-89176-292-3},
  abstract  = {Universal Dependencies (UD) is gaining popularity as an annotation standard for second language (L2) material. Grammatical errors and other interlanguage phenomena, however, pose significant challenges that official guidelines only address in part. In this paper, we give an overview of current annotation practices and provide some suggestions for harmonizing guidelines for learner corpora.}
}
```

# Changelog

* v2.17
  * initial release
* v2.18
  * added 134 sentences authored by French speakers
  * improved language metadata: replaced Swedish language names with 3-letter ISO codes
  * added a separate metadata item indicating the split (train, test or dev)
  * re-lemmatized misspellings according to https://github.com/UniversalDependencies/docs/issues/1179
  * fixed the annotation of some phrasal/nonphrasal verb according to https://github.com/UniversalDependencies/docs/issues/1132
  * started annotating syntactic calques with `CalquedLang` (cf. https://github.com/UniversalDependencies/docs/issues/1181)
  * fixed sporadic annotation errors
  * removed a duplicate sentence from the test split


<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.17
License: CC BY-SA 4.0
Includes text: yes
Parallel: no
Genre: learner-essays
Lemmas: manual native
UPOS: manual native
XPOS: not available
Features: automatic with corrections
Relations: manual native
Contributors: Masciolini, Arianna; Berdicevskis, Aleksandrs; Szawerna, Maria Irena; Grand-Clement, Caroline
Contributing: elsewhere
Contact: arianna.masciolini@gu.se
===============================================================================
</pre>
