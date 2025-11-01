# Summary

A treebank of learner Swedish based on SweLL, the Swedish Learner Language corpus.

# Introduction
UD_Swedish-SweLL is a parallel learner treebank based on [SweLL](https://spraakbanken.gu.se/en/resources/swell), the Swedish Learner Language corpus.

As of it first release, UD_Swedish-SweLL consists of a test set comprising 510 randomly selected sentences from [SweLL-gold](https://spraakbanken.gu.se/en/resources/swell-gold), a corpus of essays written by adult learners of Swedish as a second language (L2).
All essays in SweLL-gold are manually pseudonymized, error-labelled and _normalized_, i.e. accompanied by a correction hypothesis.
While the official UD 2.17 release only includes original learner sentences, such corrections are available in the [`not-to-release`](not-to-release/sv_swell-ud-test-trg.conllu) folder of this repository. 

# Annotation
Each sentence-correction pair was initially annotated with UDPipe 2 using the `swedish-talbanken-ud-2.15-241121` model and later underwent extensive manual post-correction by two annotators, who are themselves L2 Swedish speakers. 

In particular:

- __lemmas, UPOS tags and dependencies__ were checked systematically
- __morphological features__ were only checked for tokens marked as learner errors in the source corpus and/or whose automatic lemmatization, POS tagging and dependency annotation were found to be incorrect
- SweLL-gold __error labels__ are included in the MISC column and were used to automatically assign the `Typo=Yes` feature to tokens presenting orthography errors.

The general annotation principles for the annotation of interlanguage phenomena are the following:

- __token-level annotation__ (lemmatization, POS tagging and morphological analysis) should be __purely descriptive__ of the observed word forms__ (also referred to as _literal_)
- __dependency annotation__ should also be __as descriptive of the observed language use as possible, but grounded in the correction hypothesis__ of the sentence whenever different interpretations of the learner's intended meaning would lead to different analyses. This is to ensure comparability between learner productions and their corrections
3. in general, __annotation__ should be __aware of transfer phenomena__.


For a more comprehensive discussion of these principles, see [_Annotating Second Language in Universal Dependencies: a Review of Current Practices and Directions for Harmonized Guidelines_](https://aclanthology.org/2025.udw-1.17/) (Masciolini et al., UDW-SyntaxFest 2025) as well as the annotation guidelines for UD_Swedish-SweLL, available in the [`not-to-release`](not-to-release/) folder. 

In rare cases (6 tokens), these principles clash with current UD validation rules. 
When this happened, annotation was adjusted to comply with the general guidelines and the annotator's preferred analysis was moved to the MISC column under the key `IntendedXXX` (at the moment, only `IntendedDeprel` and `IntendedLemma` are attested).
This is, however, a temporary workaround pending a community discussion.

## Metadata
SweLL-gold comes with rich learner metadata that cannot be redistributed in full due to licensing restrictions.
We currently include:

- `l1`: the first language(s) of the author of the essay*
- `approximate_level`: `Nybörjare` (beginner), `Fortsättning` (intermediate) or `Avancerad` (advanced)
- `writing_language`: the language in which the author of the sentence has better written proficiency*
- `sent_id`: the sentence ID, whose format is `org-N-test` for original learner productions and `trg-N-test` for the corresponding correction hypotheses (`N` is a sequential ID)
- `text`: the full text of the sentence (pre-tokenized)

*in Swedish, planned to be replaced with ISO codes

# Acknowledgments
The manual annotation work has been carried out by Arianna Masciolini, Aleksandrs Berdicevskis and Maria Irena Szawerna, who thank Elena Volodina for her work on the source corpus, as well as for her participation in the initial UD annotation experiments.


# Contributing
If you spot annotation error or inconsistency, please open an issue in this repository.
For practical and legal reason, however, the annotation work is carried out in a private repository where we have access to all learner metadata.
If you want to get involved, you are much welcome get in touch with the treebank's maintainer at arianna.masciolini@gu.se.

# References
A paper describing UD_Swedish-SweLL is currently in preparation.
Meanwhile, if you use the treebank in you work, you are encouraged to cite _SweLL with pride: How to put a learner corpus to good use_ (Volodina et al., Huminfra Handbook - forthcoming):

```bibtex
@article{swell_with_pride,
  title        = {{SweLL} with pride: How to put a learner corpus to good use},
  author       = {Volodina, Elena and Masciolini, Arianna and Megyesi, Beáta and Prentice, Julia and Rudebeck, Lisa and Sundberg, Gunlög and Wirén, Mats},
  year         = 2025,
  journal      = {Huminfra Handbook (forthcoming)},
}
```

For more up-to-date citation information, check out the `dev` branch of this repository.

# Changelog

* 2025-11-15 v2.17
  * Initial release in Universal Dependencies.


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
Contributors: Masciolini, Arianna; Berdicevskis, Aleksandrs; Szawerna, Maria Irena
Contributing: elsewhere
Contact: arianna.masciolini@gu.se
===============================================================================
</pre>
