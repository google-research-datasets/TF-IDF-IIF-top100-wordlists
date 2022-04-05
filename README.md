# TF-IIF lists

This repository contains wordlists for a collection of languages containing words that we believe to be distinctive to each language. They are specifically selected to be the words that are more indicative of these languages and not of those languages that are common on the internet, like English.  There are 1288 language varieties represented, and each language’s word list has 1000 distinctive words. 

These wordlists are created with the `TF-IIF` formulation, which is a variant on the well-known [tf-idf](https://en.wikipedia.org/wiki/Tf%E2%80%93idf) technique, that replaces the `IDF` term with the total frequency of this word on a sample of the internet (the “inverse Internet Frequency”, or “IIF”). For more details on their construction and usage, please check out our [paper](https://arxiv.org/abs/2010.14571). Since this technique doesn’t make sense for languages that are highly prevalent on the internet, like English, those languages are not included.

This is not an officially supported Google product.


## Caveats and Notes

Please note that these wordlists are by no means a silver bullet for data filtering! For some languages they may be too high recall and for others too low. You’ll need to put in some elbow grease to make sure they are doing what you intend for your application. Furthermore, they have a few known issues that are detailed in the following sections.

### Wordlists are less effective on highly inflecting languages

Wordlist-based filtering will be less effective for morphologically rich languages, especially agglutinative or polysynthetic languages, where words are built of many smaller units of meaning (morphemes).

### Wordlists are omitted for languages with scripts that require segmentation

We don’t include word lists for languages that don’t use spaces, like Myanmar (Burmese). While this is possible, it requires the user to have access to a word segmenter for that language -- and since segmenters vary in their word splitting choices, wordlists are likely of limited utility. The omitted scripts and languages are as follows:

Script | language
---|---
Kore	 | ko
Khmr	| km
Laoo	| lo kjg
Mymr	| my mnw shn ksw rki kyu kjp
Thai	| th kxm urk bzi pww
Tibt	| bo dz lep-Tibt


### Wordlists are omitted for high-resource languages

TF-IIF lists only make sense in the context of low-resource languages. The reason for this is that the IIF term is meant to upweight tokens from languages that are not common on the internet. For a higher-resource language, it would upweight random, uncommon tokens.

### Wordlists are omitted for the most common language per script

These are omitted for the same reason that high-resource languages are upweighted; the most common language per script will account for most tokens in the relevant script. This removes the following: `en zh ko ja ru th fa ta el hi hy ml te iw kn my bn gu lo si km am pa ka or bo dv yue syr iu mni-Mtei ber chr bm-Nkoo got sat ccp lis su-Sund cjm jv-Java syl-Sylo saz tdd ban-Bali blt osa btm`

### Domain Effects

The datasets from which these datasets were created are largely from 1)
internal, curated data; 2) Wikipedia, and 3) crawls of public target-language web pages.

In general, the most frequent tokens in a language should be very common
words, and not vary much depending on the dataset. However, since some of the source datasets were small or narrow-domain, a few of these wordlists may be less useful practically. Furthermore, because of the TF-IIF formulation, if
these languages are closer to common languages on the internet, these effects
will be exacerbated. For this reason we don’t include wordlists for common languages on the internet like English or Hindi.

## Note about the second version

This repository originally contained wordlists for only 510 languages, with the top 100 words per language. The 2022 update increased the language coverage and number of words per language. It also slightly improved the formulation, e.g. removing the `IDF` term and removing capitalization.


## Pull requests

We did our best to ensure quality, but these lists were automatically selected, and therefore have various issues! If you find issues, feel free to send us a pull request and we’ll look into incorporating your feedback.	


