# Guidelines for the annotation of interlanguage phenomena in UD_Swedish-SweLL

(NOTE: the examples in this file are SVG snippets that the GitHub Markdown previewer does not fully render at the time of writing. If you can't see any dependency trees, try downloading this file and opening it with a different Markdown renderer or copy its source [here](https://markdownlivepreview.com/))

## Contents

<!-- TOC -->

- [Guidelines for the annotation of interlanguage phenomena in UD_Swedish-SweLL](#guidelines-for-the-annotation-of-interlanguage-phenomena-in-ud_swedish-swell)
    - [Contents](#contents)
    - [General principles](#general-principles)
    - [Guidelines for specific phenomena](#guidelines-for-specific-phenomena)
        - [Over-segmentation](#over-segmentation)
            - [Words](#words)
            - [Sentences](#sentences)
        - [Under-segmentation](#under-segmentation)
            - [Words](#words)
            - [Sentences](#sentences)
        - [Typos/spelling errors](#typosspelling-errors)
        - [Redundant words S-R](#redundant-words-s-r)
            - [Redundant adpositions](#redundant-adpositions)
            - [Unclear usage and/or unrecognizable word](#unclear-usage-andor-unrecognizable-word)
        - [Missing words S-M](#missing-words-s-m)
            - [Missing heads](#missing-heads)
            - [Missing adpositions](#missing-adpositions)
    - [Wrong POS](#wrong-pos)

<!-- /TOC -->


## General principles

1. __token-level annotation__ (lemmatization, POS tagging and morphological analysis) should be __purely descriptive__ of the observed word forms (also referred to as _literal_)
2. __dependency annotation__ should also be __as descriptive of the observed language use as possible, but grounded in the correction hypothesis__ of the sentence whenever different interpretations of the learner's intended meaning would lead to different analyses. This is to ensure comparability between learner productions and their corrections
3. in general, __annotation__ should be __aware of transfer phenomena__.

In practice, 1. means that, whenever possible:

- derivation and orthography errors are preserved in the lemmas
- UPOS tags and morphological features are assigned based on the observed word forms rather than the context in which they occur and the syntactic role they fill

Principle 2. has three more practical implications:

- dependency heads and relation types describe the way in which a given token is used (_distributional annotation_), even if this means assigning a label incompatible with its UPOS tag or lemma
- when distributional criteria alone are not sufficient to unambiguously decide on an interpretation of the learner sentence, the analysis of its correction hypothesis is used as a starting point
- each learner sentence-correction pair is annotated in parallel to ensure that their analyses are consistent with each other.

> __Example:__ "båda" is tagged as a (plural) `ADJ` but assigned the relation type `cc` because it is used like the coordinating conjunction "både".
>
><svg width="297"
>     height="115"
>     viewBox="0 0 297 115"
>     version="1.1"
>     xmlns="http://www.w3.org/2000/svg">
>  <text x="5" y="108" font-size="14">från</text>
>  <text x="51" y="108" font-size="14">båda</text>
>  <text x="97" y="108" font-size="14">mamma</text>
>  <text x="152" y="108" font-size="14">och</text>
>  <text x="207" y="108" font-size="14">pappa</text>
>  <text x="5" y="93" font-size="14">ADP</text>
>  <text x="51" y="93" font-size="14">ADJ</text>
>  <text x="97" y="93" font-size="14">NOUN</text>
>  <text x="152" y="93" font-size="14">CCONJ</text>
>  <text x="207" y="93" font-size="14">NOUN</text>
>  <path d="M 17 80 Q 17 47 50 47 L 72 47 Q 105 47 105 80"
>        stroke="black"
>        fill="none"/>
>  <line x1="17" y1="75" x2="17" y2="80" stroke="black"/>
>  <path d="M 17 80 14 74 20 74"/>
>  <text x="52" y="42" font-size="10">case</text>
>  <path d="M 64 80 Q 64 63 81 63 L 87 63 Q 104 63 104 80"
>        stroke="black"
>        fill="none"/>
>  <line x1="64" y1="75" x2="64" y2="80" stroke="black"/>
>  <path d="M 64 80 61 74 67 74"/>
>  <text x="77" y="58" font-size="10">cc</text>
>  <line x1="112" y1="20" x2="112" y2="80" stroke="black"/>
>  <path d="M 112 80 109 74 115 74"/>
>  <text x="117" y="28" font-size="10">root</text>
>  <path d="M 165 80 Q 165 63 181 63 L 198 63 Q 214 63 214 80"
>        stroke="black"
>        fill="none"/>
>  <line x1="165" y1="75" x2="165" y2="80" stroke="black"/>
>  <path d="M 165 80 162 74 168 74"/>
>  <text x="185" y="58" font-size="10">cc</text>
>  <path d="M 118 80 Q 118 47 152 47 L 192 47 Q 226 47 226 80"
>        stroke="black"
>        fill="none"/>
>  <line x1="226" y1="75" x2="226" y2="80" stroke="black"/>
>  <path d="M 226 80 223 74 229 74"/>
>  <text x="163" y="42" font-size="10">conj</text>
></svg>

Principle 3 is implemented by borrowing guidelines from the learner's L1(s) and/or best writing language when they use constructions that mimic one of those languages. 
This is in agreement with the Italian-VALICO guidelines for syntactic calques.


> __Example__: The learner is a speaker of English, so "bus resa" is annotated as an English `compound`, even though Swedish-specific guidelines recommend only using this label for foreign expressions.
>
> <svg width="205" height="135" viewBox="0 0 205 135" version="1.1" xmlns="http://www.w3.org/2000/svg">
>  <text x="5" y="128" font-size="16">en</text>
>  <text x="42" y="128" font-size="16">lång</text>
>  <text x="88" y="128" font-size="16">bus</text>
>  <text x="134" y="128" font-size="16">resa</text>
>  <text x="5" y="113" font-size="10">DET</text>
>  <text x="42" y="113" font-size="10">ADJ</text>
>  <text x="88" y="113" font-size="10">NOUN</text>
>  <text x="134" y="113" font-size="10">NOUN</text>
>  <path d="M 16 100 Q 16 50 66 50 L 93 50 Q 143 50 143 100" stroke="black" fill="none"></path>
>  <line x1="16" y1="95" x2="16" y2="100" stroke="black"></line>
>  <path d="M 16 100 13 94 19 94"></path>
>  <text x="73" y="45" font-size="10">det</text>
>  <path d="M 54 100 Q 54 67 87 67 L 109 67 Q 142 67 142 100" stroke="black" fill="none"></path>
>  <line x1="54" y1="95" x2="54" y2="100" stroke="black"></line>
>  <path d="M 54 100 51 94 57 94"></path>
>  <text x="89" y="62" font-size="10">amod</text>
>  <path d="M 101 100 Q 101 83 118 83 L 124 83 Q 141 83 141 100" stroke="black" fill="none"></path>
>  <line x1="101" y1="95" x2="101" y2="100" stroke="black"></line>
>  <path d="M 101 100 98 94 104 94"></path>
>  <text x="103" y="78" font-size="10">compound</text>
>  <line x1="149" y1="20" x2="149" y2="100" stroke="black"></line>
>  <path d="M 149 100 146 94 152 94"></path>
>  <text x="154" y="28" font-size="10">root</text>
></svg>

## Guidelines for specific phenomena

### Over-segmentation

#### Words
If the incorrectly split elements are two recognizable Swedish words, the `DEPREL` is assigned based on [distributional criteria](#literal-reading-at-the-token-level-distributional-criteria-at-the-structural-level) and/or [L1 guidelines](#guidelines-from-the-learners-l1s-can-be-borrowed-when-the-constructions-used-mimic-such-languages) (cf. examples 1-2 below). 

Otherwise, we follow standard guidelines and use [`goeswith`](https://universaldependencies.org/u/dep/goeswith.html).
`goeswith` is also used when the first element is a prefix and is clearly used as such, even though it also happens to exist as a recognizable word (cf. example 3).

> __Example 1__:
> 
> <svg width="147" height="95" viewBox="0 0 147 95" version="1.1" xmlns="http://www.w3.org/2000/svg">
>   <text x="5" y="88" font-size="16">tänkar</text>
>   <text x="69" y="88" font-size="16">tagande</text>
>   <text x="5" y="73" font-size="10">NOUN</text>
>   <text x="69" y="73" font-size="10">ADJ</text>
>   <path d="M 17 60 Q 17 43 34 43 L 60 43 Q 77 43 77 60" stroke="black" fill="none"></path>
>   <line x1="17" y1="55" x2="17" y2="60" stroke="black"></line>
>   <path d="M 17 60 14 54 20 54"></path>
>   <text x="29" y="38" font-size="10">compound</text>
>   <line x1="84" y1="20" x2="84" y2="60" stroke="black"></line>
>   <path d="M 84 60 81 54 87 54"></path>
>   <text x="89" y="28" font-size="10">root</text>
> </svg>
>
> __Example 2__:
> 
> <svg width="268" height="115" viewBox="0 0 268 115" version="1.1" xmlns="http://www.w3.org/2000/svg">
>  <text x="5" y="108" font-size="16">Mitt</text>
>  <text x="51" y="108" font-size="16">favoritt</text>
>  <text x="133" y="108" font-size="16">plats</text>
>  <text x="188" y="108" font-size="16">?</text>
>  <text x="5" y="93" font-size="10">PRON</text>
>  <text x="51" y="93" font-size="10">ADJ</text>
>  <text x="133" y="93" font-size="10">NOUN</text>
>  <text x="188" y="93" font-size="10">PUNCT</text>
>  <path d="M 16 80 Q 16 47 50 47 L 108 47 Q 142 47 142 80" stroke="black" fill="none"></path>
>  <line x1="16" y1="75" x2="16" y2="80" stroke="black"></line>
>  <path d="M 16 80 13 74 19 74"></path>
>  <text x="59" y="42" font-size="10">nmod:poss</text>
>  <path d="M 63 80 Q 63 63 79 63 L 125 63 Q 141 63 141 80" stroke="black" fill="none"></path>
>  <line x1="63" y1="75" x2="63" y2="80" stroke="black"></line>
>  <path d="M 63 80 60 74 66 74"></path>
>  <text x="93" y="58" font-size="10">amod</text>
>  <line x1="148" y1="20" x2="148" y2="80" stroke="black"></line>
>  <path d="M 148 80 145 74 151 74"></path>
>  <text x="153" y="28" font-size="10">root</text>
>  <path d="M 156 80 Q 156 63 172 63 L 189 63 Q 205 63 205 80" stroke="black" fill="none"></path>
>  <line x1="205" y1="75" x2="205" y2="80" stroke="black"></line>
>  <path d="M 205 80 202 74 208 74"></path>
>  <text x="169" y="58" font-size="10">punct</text>
></svg>
> 
> 
> __Example 3__:
>
> <svg width="223" height="115" viewBox="0 0 223 115" version="1.1" xmlns="http://www.w3.org/2000/svg">
>   <text x="5" y="108" font-size="16">det</text>
>   <text x="51" y="108" font-size="16">är</text>
>   <text x="88" y="108" font-size="16">jätte</text>
>   <text x="134" y="108" font-size="16">roligt</text>
>   <text x="5" y="93" font-size="10">PRON</text>
>   <text x="51" y="93" font-size="10">AUX</text>
>   <text x="88" y="93" font-size="10">ADJ</text>
>   <text x="134" y="93" font-size="10">X</text>
>   <path d="M 17 80 Q 17 47 50 47 L 63 47 Q 96 47 96 80" stroke="black" fill="none"></path>
>   <line x1="17" y1="75" x2="17" y2="80" stroke="black"></line>
>   <path d="M 17 80 14 74 20 74"></path>
>   <text x="45" y="42" font-size="10">nsubj</text>
>   <path d="M 65 80 Q 65 63 79 63 L 79 63 Q 94 63 94 80" stroke="black" fill="none"></path>
>   <line x1="65" y1="75" x2="65" y2="80" stroke="black"></line>
>   <path d="M 65 80 62 74 68 74"></path>
>   <text x="73" y="58" font-size="10">cop</text>
>   <line x1="103" y1="20" x2="103" y2="80" stroke="black"></line>
>   <path d="M 103 80 100 74 106 74"></path>
>   <text x="108" y="28" font-size="10">root</text>
>   <path d="M 111 80 Q 111 63 128 63 L 134 63 Q 151 63 151 80" stroke="black" fill="none"></path>
>   <line x1="151" y1="75" x2="151" y2="80" stroke="black"></line>
>   <path d="M 151 80 148 74 154 74"></path>
>   <text x="113" y="58" font-size="10">goeswith</text>
> </svg>

#### Sentences
In original-correction pairs where the original consists of 2 (or potentially more) orthographical sentences, dependency annotation follows that of the correction as closely as possible and redundant punctuation is attached to the head of the orthographical sentence following it.

> __Example__:
>
> <svg width="864" height="135" viewBox="0 0 864 135" version="1.1" xmlns="http://www.w3.org/2000/svg">
>  <text x="5" y="128" font-size="16">När</text>
>  <text x="60" y="128" font-size="16">jag</text>
>  <text x="106" y="128" font-size="16">känner</text>
>  <text x="170" y="128" font-size="16">mig</text>
>  <text x="216" y="128" font-size="16">mår</text>
>  <text x="262" y="128" font-size="16">inte</text>
>  <text x="308" y="128" font-size="16">bra</text>
>  <text x="345" y="128" font-size="16">.</text>
>  <text x="400" y="128" font-size="16">Jag</text>
>  <text x="446" y="128" font-size="16">går</text>
>  <text x="492" y="128" font-size="16">utt</text>
>  <text x="529" y="128" font-size="16">och</text>
>  <text x="584" y="128" font-size="16">promenerar</text>
>  <text x="684" y="128" font-size="16">.</text>
>  <text x="5" y="113" font-size="10">SCONJ</text>
>  <text x="60" y="113" font-size="10">PRON</text>
>  <text x="106" y="113" font-size="10">VERB</text>
>  <text x="170" y="113" font-size="10">PRON</text>
>  <text x="216" y="113" font-size="10">VERB</text>
>  <text x="262" y="113" font-size="10">PART</text>
>  <text x="308" y="113" font-size="10">ADV</text>
>  <text x="345" y="113" font-size="10">PUNCT</text>
>  <text x="400" y="113" font-size="10">PRON</text>
>  <text x="446" y="113" font-size="10">VERB</text>
>  <text x="492" y="113" font-size="10">ADV</text>
>  <text x="529" y="113" font-size="10">CCONJ</text>
>  <text x="584" y="113" font-size="10">VERB</text>
>  <text x="684" y="113" font-size="10">PUNCT</text>
>  <path d="M 16 100 Q 16 67 50 67 L 81 67 Q 115 67 115 100" stroke="black" fill="none"></path>
>  <line x1="16" y1="95" x2="16" y2="100" stroke="black"></line>
>  <path d="M 16 100 13 94 19 94"></path>
>  <text x="57" y="62" font-size="10">mark</text>
>  <path d="M 73 100 Q 73 83 90 83 L 96 83 Q 113 83 113 100" stroke="black" fill="none"></path>
>  <line x1="73" y1="95" x2="73" y2="100" stroke="black"></line>
>  <path d="M 73 100 70 94 76 94"></path>
>  <text x="82" y="78" font-size="10">nsubj</text>
>  <path d="M 116 100 Q 116 50 166 50 L 406 50 Q 456 50 456 100" stroke="black" fill="none"></path>
>  <line x1="116" y1="95" x2="116" y2="100" stroke="black"></line>
>  <path d="M 116 100 113 94 119 94"></path>
>  <text x="275" y="45" font-size="10">advcl</text>
>  <path d="M 128 100 Q 128 83 145 83 L 171 83 Q 188 83 188 100" stroke="black" fill="none"></path>
>  <line x1="188" y1="95" x2="188" y2="100" stroke="black"></line>
>  <path d="M 188 100 185 94 191 94"></path>
>  <text x="151" y="78" font-size="10">obj</text>
>  <path d="M 127 100 Q 127 67 161 67 L 201 67 Q 235 67 235 100" stroke="black" fill="none"></path>
>  <line x1="235" y1="95" x2="235" y2="100" stroke="black"></line>
>  <path d="M 235 100 232 94 238 94"></path>
>  <text x="170" y="62" font-size="10">xcomp</text>
>  <path d="M 239 100 Q 239 83 256 83 L 262 83 Q 279 83 279 100" stroke="black" fill="none"></path>
>  <line x1="279" y1="95" x2="279" y2="100" stroke="black"></line>
>  <path d="M 279 100 276 94 282 94"></path>
>  <text x="245" y="78" font-size="10">advmod</text>
>  <path d="M 238 100 Q 238 67 271 67 L 293 67 Q 326 67 326 100" stroke="black" fill="none"></path>
>  <line x1="326" y1="95" x2="326" y2="100" stroke="black"></line>
>  <path d="M 326 100 323 94 329 94"></path>
>  <text x="269" y="62" font-size="10">advmod</text>
>  <path d="M 356 100 Q 356 67 390 67 L 421 67 Q 455 67 455 100" stroke="black" fill="none"></path>
>  <line x1="356" y1="95" x2="356" y2="100" stroke="black"></line>
>  <path d="M 356 100 353 94 359 94"></path>
>  <text x="394" y="62" font-size="10">punct</text>
>  <path d="M 413 100 Q 413 83 430 83 L 436 83 Q 453 83 453 100" stroke="black" fill="none"></path>
>  <line x1="413" y1="95" x2="413" y2="100" stroke="black"></line>
>  <path d="M 413 100 410 94 416 94"></path>
>  <text x="422" y="78" font-size="10">nsubj</text>
>  <line x1="461" y1="20" x2="461" y2="100" stroke="black"></line>
>  <path d="M 461 100 458 94 464 94"></path>
>  <text x="466" y="28" font-size="10">root</text>
>  <path d="M 469 100 Q 469 83 486 83 L 492 83 Q 509 83 509 100" stroke="black" fill="none"></path>
>  <line x1="509" y1="95" x2="509" y2="100" stroke="black"></line>
>  <path d="M 509 100 506 94 512 94"></path>
>  <text x="462" y="78" font-size="10">compound:prt</text>
>  <path d="M 542 100 Q 542 83 558 83 L 575 83 Q 591 83 591 100" stroke="black" fill="none"></path>
>  <line x1="542" y1="95" x2="542" y2="100" stroke="black"></line>
>  <path d="M 542 100 539 94 545 94"></path>
>  <text x="562" y="78" font-size="10">cc</text>
>  <path d="M 467 100 Q 467 67 500 67 L 570 67 Q 603 67 603 100" stroke="black" fill="none"></path>
>  <line x1="603" y1="95" x2="603" y2="100" stroke="black"></line>
>  <path d="M 603 100 600 94 606 94"></path>
>  <text x="526" y="62" font-size="10">conj</text>
>  <path d="M 467 100 Q 467 50 517 50 L 653 50 Q 703 50 703 100" stroke="black" fill="none"></path>
>  <line x1="703" y1="95" x2="703" y2="100" stroke="black"></line>
>  <path d="M 703 100 700 94 706 94"></path>
>  <text x="574" y="45" font-size="10">punct</text>
></svg>

### Under-segmentation

#### Words
We follow Korean-KSL and treat under-segmented words as single tokens. 
`UPOS` and `DEPREL` are determined based on what would be the syntactic head if the words was correctly segmented. 

#### Sentences
If an original learner sentence is re-segmented into two sentences by the corrector, the two sentences in the correction are treated as a single unit and linked with a `parataxis` relation.

### Typos/spelling errors
Following Italian-Valico, single-token typos and orthographical errors are, whenever possible, lemmatized preserving the errors they contain. 
For instance:

| `FORM` | `LEMMA` | corrected `LEMMA` | `CorrectionLabel` | comments |
| --- | --- | --- | --- | --- |
| traffik | traffik | trafik | O | simple misspelling |
| förslagor | förslaga | förslag | M-F | lemma based on the gender of the incorrect form |
| Landerna | land | land | O | misspelling that cannot be preserved |
| däref$nt | däref$nt | därefter | O | major misspelling left as is |

Rationale:

- if we use the corrected lemma, some information is lots, especially when it comes to morphological inflection errors (`M`). _förslaga_, for instance, with `Gender=Com`, which is coherent with the observed form, whereas the correct lemma, _förslag_ forces `Gender=Neut`
- since this is a parallel treebank, the correct lemma can always be retrieved from the correction hypothesis (and added as a `CorrectLemma` in `MISC`).

### Redundant words (`S-R`)
Redundant (typically function) words (correction-labelled as `S-R`, i.e. Syntax - Redundant) can often be annotated straightforwardly (e.g. "tänker __att__ stänga" is annotated as `PART`+`mark`). 
However, there are a number of challenging subcases.

#### Redundant adpositions
Annotation of adpositions themselves is unproblematic (`ADP` + `case`), but it is less clear what to do with the nominals they refer to.
We use `obl`.

> __Example__:
>
> <svg width="232" height="135" viewBox="0 0 232 135" version="1.1" xmlns="http://www.w3.org/2000/svg">
>   <text x="5" y="128" font-size="16">Krama</text>
>   <text x="60" y="128" font-size="16">till</text>
>   <text x="106" y="128" font-size="16">träd</text>
>   <text x="152" y="128" font-size="16">.</text>
>   <text x="5" y="113" font-size="10">VERB</text>
>   <text x="60" y="113" font-size="10">ADP</text>
>   <text x="106" y="113" font-size="10">NOUN</text>
>   <text x="152" y="113" font-size="10">PUNCT</text>
>   <line x1="20" y1="20" x2="20" y2="100" stroke="black"></line>
>   <path d="M 20 100 17 94 23 94"></path>
>   <text x="25" y="28" font-size="10">root</text>
>   <path d="M 73 100 Q 73 83 90 83 L 96 83 Q 113 83 113 100" stroke="black" fill="none"></path>
>   <line x1="73" y1="95" x2="73" y2="100" stroke="black"></line>
>   <path d="M 73 100 70 94 76 94"></path>
>   <text x="84" y="78" font-size="10">case</text>
>   <path d="M 26 100 Q 26 67 60 67 L 91 67 Q 125 67 125 100" stroke="black" fill="none"></path>
>   <line x1="125" y1="95" x2="125" y2="100" stroke="black"></line>
>   <path d="M 125 100 122 94 128 94"></path>
>   <text x="69" y="62" font-size="10">obl</text>
>   <path d="M 26 100 Q 26 50 76 50 L 121 50 Q 171 50 171 100" stroke="black" fill="none"></path>
>   <line x1="171" y1="95" x2="171" y2="100" stroke="black"></line>
>   <path d="M 171 100 168 94 174 94"></path>
>   <text x="87" y="45" font-size="10">punct</text>
> </svg>


This is in line English-ESL, Italian-VALICO and Russian.

#### Unclear usage and/or unrecognizable word

If the usage of the word is unclear, we revert to `dep`.
If the `UPOS` of the word is ambiguous or if the word is unrecognizable, the tag `X` is used.

> __Example__:
>
> <svg width="326" height="155" viewBox="0 0 326 155" version="1.1" xmlns="http://www.w3.org/2000/svg">
>   <text x="5" y="148" font-size="16">att</text>
>   <text x="51" y="148" font-size="16">stänga</text>
>   <text x="115" y="148" font-size="16">som</text>
>   <text x="152" y="148" font-size="16">den</text>
>   <text x="189" y="148" font-size="16">fin</text>
>   <text x="226" y="148" font-size="16">plats</text>
>   <text x="5" y="133" font-size="10">PART</text>
>   <text x="51" y="133" font-size="10">VERB</text>
>   <text x="115" y="133" font-size="10">X</text>
>   <text x="152" y="133" font-size="10">DET</text>
>   <text x="189" y="133" font-size="10">ADJ</text>
>   <text x="226" y="133" font-size="10">NOUN</text>
>   <path d="M 18 120 Q 18 103 35 103 L 41 103 Q 58 103 58 120" stroke="black" fill="none"></path>
>   <line x1="18" y1="115" x2="18" y2="120" stroke="black"></line>
>   <path d="M 18 120 15 114 21 114"></path>
>   <text x="29" y="98" font-size="10">mark</text>
>   <line x1="66" y1="20" x2="66" y2="120" stroke="black"></line>
>   <path d="M 66 120 63 114 69 114"></path>
>   <text x="71" y="28" font-size="10">root</text>
>   <path d="M 126 120 Q 126 70 176 70 L 185 70 Q 235 70 235 120" stroke="black" fill="none"></path>
>   <line x1="126" y1="115" x2="126" y2="120" stroke="black"></line>
>   <path d="M 126 120 123 114 129 114"></path>
>   <text x="174" y="65" font-size="10">dep</text>
>   <path d="M 164 120 Q 164 87 197 87 L 201 87 Q 234 87 234 120" stroke="black" fill="none"></path>
>   <line x1="164" y1="115" x2="164" y2="120" stroke="black"></line>
>   <path d="M 164 120 161 114 167 114"></path>
>   <text x="192" y="82" font-size="10">det</text>
>   <path d="M 203 120 Q 203 103 217 103 L 217 103 Q 232 103 232 120" stroke="black" fill="none"></path>
>   <line x1="203" y1="115" x2="203" y2="120" stroke="black"></line>
>   <path d="M 203 120 200 114 206 114"></path>
>   <text x="209" y="98" font-size="10">amod</text>
>   <path d="M 72 120 Q 72 53 139 53 L 178 53 Q 245 53 245 120" stroke="black" fill="none"></path>
>   <line x1="245" y1="115" x2="245" y2="120" stroke="black"></line>
>   <path d="M 245 120 242 114 248 114"></path>
>   <text x="152" y="48" font-size="10">obj</text>
> </svg>

### Missing words (`S-M`)
In some cases (e.g. modifiers), missing words do not raise any questions.
Missing heads and adpositions (and possibly other function words), however, pose some specific problems.

#### Missing heads
As Chinese-CFL and Russian, we follow the guidelines for [promotion by head elision](https://universaldependencies.org/u/overview/syntax.html#promotion-by-head-elision) and [ellipsis](https://universaldependencies.org/u/overview/specific-syntax.html#ellipsis).

#### Missing adpositions
Similar to [Redundant adposition](#redundant-adpositions), but easier: we use the `DEPREL` `obl` in both original and target, which is coherent with our overarching principles, as well as with the fact that obliques are not necessarily prepositional.

## Wrong POS
We assign the `UPOS` and `FEATS` based on the surface form, the `DEPREL` based on the function the token plays in the sentence.