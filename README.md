<!-- 
BSD 3-Clause License
Copyright (c) 2022, GM Consult Pty Ltd
All rights reserved. 
-->

[![GM Consult Pty Ltd](https://raw.githubusercontent.com/GM-Consult-Pty-Ltd/sir_flutter/main/doc/images/header.png?raw=true "GM Consult Pty Ltd")](https://github.com/GM-Consult-Pty-Ltd)
## ***Dictionary*, *thesaurus* and *term expansion* utilities used in *natural language processing (NLP)*.**

A system for information retrieval in Flutter.

*THIS PACKAGE IS **PRE-RELEASE**, IN ACTIVE DEVELOPMENT AND SUBJECT TO DAILY BREAKING CHANGES.*

## Contents:
- [Overview](#overview)
- [Usage](#usage)
- [API](#api)
- [Definitions](#definitions)
- [References](#references)
- [Issues](#issues)

## Overview

TODO: Overview

Refer to the [references](#references) to learn more about the theory behind this library.

(*[back to top](#)*)

## Usage

In the `pubspec.yaml` of your flutter project, add the following dependency:

```yaml
dependencies:
  sir_flutter: <latest_version>
```

In your code file add the following import:

(*[back to top](#)*)

```dart
import 'package:sir_flutter/sir_flutter.dart';
```

TODO: describe usage.

(*[back to top](#)*)

## API

The [API](https://pub.dev/documentation/sir_flutter/latest/) exposes

TODO: describe the API

(*[back to top](#)*)

## Definitions

The following definitions are used throughout the [documentation](https://pub.dev/documentation/text_analysis/latest/):

* `corpus`- the collection of `documents` for which an `index` is maintained.
* `character filter` - filters characters from text in preparation of tokenization.  
* `Damerau–Levenshtein distance` - a metric for measuring the `edit distance` between two `terms` by counting the minimum number of operations (insertions, deletions or substitutions of a single character, or transposition of two adjacent characters) required to change one `term` into the other.
* `dictionary (in an index)` - a hash of `terms` (`vocabulary`) to the frequency of occurence in the `corpus` documents.
* `document` - a record in the `corpus`, that has a unique identifier (`docId`) in the `corpus`'s primary key and that contains one or more text fields that are indexed.
* `document frequency (dFt)` - the number of documents in the `corpus` that contain a term.
* `edit distance` - a measure of how dissimilar two terms are by counting the minimum number of operations required to transform one string into the other (from [Wikipedia](https://en.wikipedia.org/wiki/Edit_distance)).
- `Flesch reading ease score` - a readibility measure calculated from  sentence length and word length on a 100-point scale. The higher the score, the easier it is to understand the document (from [Wikipedia](https://en.wikipedia.org/wiki/Flesch%E2%80%93Kincaid_readability_tests)).
- `Flesch-Kincaid grade level` - a readibility measure relative to U.S. school grade level.  It is also calculated from sentence length and word length (from [Wikipedia](https://en.wikipedia.org/wiki/Flesch%E2%80%93Kincaid_readability_tests)).
* `index` - an [inverted index](https://en.wikipedia.org/wiki/Inverted_index) used to look up `document` references from the `corpus` against a `vocabulary` of `terms`. 
* `index-elimination` - selecting a subset of the entries in an index where the `term` is in the collection of `terms` in a search phrase.
* `inverse document frequency (iDft)` - a normalized measure of how rare a `term` is in the corpus. It is defined as `log (N / dft)`, where N is the total number of terms in the index. The `iDft` of a rare term is high, whereas the `iDft` of a frequent term is likely to be low.
* `Jaccard index` measures similarity between finite sample sets, and is defined as the size of the intersection divided by the size of the union of the sample sets (from [Wikipedia](https://en.wikipedia.org/wiki/Jaccard_index)).
* `Map<String, dynamic>` is an acronym for `"Java Script Object Notation"`, a common format for persisting data.
* `k-gram` - a sequence of (any) k consecutive characters from a `term`. A `k-gram` can start with "$", denoting the start of the term, and end with "$", denoting the end of the term. The 3-grams for "castle" are { $ca, cas, ast, stl, tle, le$ }.
* `lemma  or lemmatizer` - lemmatisation (or lemmatization) in linguistics is the process of grouping together the inflected forms of a word so they can be analysed as a single item, identified by the word's lemma, or dictionary form (from [Wikipedia](https://en.wikipedia.org/wiki/Lemmatisation)).
* `Natural language processing (NLP)` is a subfield of linguistics, computer science, and artificial intelligence concerned with the interactions between computers and human language, in particular how to program computers to process and analyze large amounts of natural language data (from [Wikipedia](https://en.wikipedia.org/wiki/Natural_language_processing)).
* `postings` - a separate index that records which `documents` the `vocabulary` occurs in.  In a positional `index`, the postings also records the positions of each `term` in the `text` to create a positional inverted `index`.
* `postings list` - a record of the positions of a `term` in a `document`. A position of a `term` refers to the index of the `term` in an array that contains all the `terms` in the `text`. In a zoned `index`, the `postings lists` records the positions of each `term` in the `text` a `zone`.
* `stem or stemmer` -  stemming is the process of reducing inflected (or sometimes derived) words to their word stem, base or root form (generally a written word form) (from [Wikipedia](https://en.wikipedia.org/wiki/Stemming)).
* `stopwords` - common words in a language that are excluded from indexing.
* `term` - a word or phrase that is indexed from the `corpus`. The `term` may differ from the actual word used in the corpus depending on the `tokenizer` used.
* `term filter` - filters unwanted terms from a collection of terms (e.g. stopwords), breaks compound terms into separate terms and / or manipulates terms by invoking a `stemmer` and / or `lemmatizer`.
* `term expansion` - finding terms with similar spelling (e.g. spelling correction) or synonyms for a term. 
* `term frequency (Ft)` - the frequency of a `term` in an index or indexed object.
* `term position` - the zero-based index of a `term` in an ordered array of `terms` tokenized from the `corpus`.
* `text` - the indexable content of a `document`.
* `token` - representation of a `term` in a text source returned by a `tokenizer`. The token may include information about the `term` such as its position(s) (`term position`) in the text or frequency of occurrence (`term frequency`).
* `token filter` - returns a subset of `tokens` from the tokenizer output.
* `tokenizer` - a function that returns a collection of `token`s from `text`, after applying a character filter, `term` filter, [stemmer](https://en.wikipedia.org/wiki/Stemming) and / or [lemmatizer](https://en.wikipedia.org/wiki/Lemmatisation).
* `vocabulary` - the collection of `terms` indexed from the `corpus`.
* `zone` - the field or zone of a document that a term occurs in, used for parametric indexes or where scoring and ranking of search results attribute a higher score to documents that contain a term in a specific zone (e.g. the title rather that the body of a document).

(*[back to top](#)*)
## References

* [Manning, Raghavan and Schütze, "*Introduction to Information Retrieval*", Cambridge University Press, 2008](https://nlp.stanford.edu/IR-book/pdf/irbookprint.pdf)
* [University of Cambridge, 2016 "*Information Retrieval*", course notes, Dr Ronan Cummins, 2016](https://www.cl.cam.ac.uk/teaching/1516/InfoRtrv/)
* [Wikipedia (1), "*Inverted Index*", from Wikipedia, the free encyclopedia](https://en.wikipedia.org/wiki/Inverted_index)
* [Wikipedia (2), "*Lemmatisation*", from Wikipedia, the free encyclopedia](https://en.wikipedia.org/wiki/Lemmatisation)
* [Wikipedia (3), "*Stemming*", from Wikipedia, the free encyclopedia](https://en.wikipedia.org/wiki/Stemming)
* [Wikipedia (4), "*Synonym*", from Wikipedia, the free encyclopedia](https://en.wikipedia.org/wiki/Synonym)
* [Wikipedia (5), "*Jaccard Index*", from Wikipedia, the free encyclopedia](https://en.wikipedia.org/wiki/Jaccard_index)
* [Wikipedia (6), "*Flesch–Kincaid readability tests*", from Wikipedia, the free encyclopedia](https://en.wikipedia.org/wiki/Flesch%E2%80%93Kincaid_readability_tests)
* [Wikipedia (7), "*Edit distance*", from Wikipedia, the free encyclopedia](https://en.wikipedia.org/wiki/Edit_distance)
* [Wikipedia (8), "*Damerau–Levenshtein distance*", from Wikipedia, the free encyclopedia](https://en.wikipedia.org/wiki/Damerau%E2%80%93Levenshtein_distance)
* [Wikipedia (9), "*Natural language processing*", from Wikipedia, the free encyclopedia](https://en.wikipedia.org/wiki/Natural_language_processing)

(*[back to top](#)*)

## Issues

If you find a bug please fill an [issue](https://github.com/GM-Consult-Pty-Ltd/sir_flutter/issues).  

This project is a supporting package for a revenue project that has priority call on resources, so please be patient if we don't respond immediately to issues or pull requests.


