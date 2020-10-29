# TF-IDF-IIF lists
This repository contains wordlists for a collection of languages containing words that we believe to be distinctive to each language. They are specifically selected to be the words that are more indicative of these languages and not of those languages that are common on the internet, like English.  There are 508 language varieties represented, and each language’s word list has 100 distinctive words. 

These wordlists are created with the `TF-IDF-IIF` formulation, which is a variant on the well-known [tf-idf](https://en.wikipedia.org/wiki/Tf%E2%80%93idf) technique, that additionally takes into account the total frequency of this word on a sample of the internet (the “inverse Internet Frequency”, or “IIF”). For more details on their construction and usage, please check out our [paper](https://arxiv.org/abs/2010.14571.). Since this technique doesn’t make sense for languages that are highly prevalent on the internet, like English, those languages are not included.

This is not an officially supported Google product.


## Caveats and Notes

Please note that these wordlists are by no means a silver bullet for data filtering! For some languages they may be too high recall and for others too low. You’ll need to put in some elbow grease to make sure they are doing what you intend for your application. Furthermore, they have a few known issues that are detailed in the following sections.

### Domain Effects

The datasets from which these datasets were created are largely from 1)
internal, curated data; 2) Wikipedia, and 3) crawls of public target-language web pages.

In general, the most frequent tokens in a language should be very common
words, and not vary much depending on the dataset. However, since some of the source datasets were small or narrow-domain, a few of these wordlists may be less useful practically. Furthermore, because of the TF-IIF-IDF formulation, if
these languages are closer to common languages on the internet, these effects
will be exacerbated. For this reason we don’t include wordlists for common languages on the internet like English or Hindi.

A few datasets have high interference from templated Wikipedia data. The most common templates are from census data, and are characterized by words like “municipality” and “commune”. We have removed some of these, but many still remain, especially in non-Latin and non-Cyrillic scripts.  An approximate list of languages with heavy Wikipedia influence (which may or may not be templated) is `ace, ady, an, arz, ast, av, ba, bar, bi, bik, bjn, bm, br, bxm, cdo, chr, csb, ee, egl, ext, fj, fo, fur, glk, gn, gsw, gv, hak, hif, hsb, ia, ilo, jam, kaa-Latn, kbd, koi, krc, ksh, kw, la, lad, lez, lg, li, lij, lmo, lrc, mrj, myv, mzn, nap, nds, new, nso, nv, oc, olo, om, os, pag, pam, pap, pfl, pms, qu, rm, rn, rom, rue, rw, sa, sah, sc, scn, sco, se, srn, szl, tcy, tk, to, tpi, tt, tyv, udm, vec, vep, vls, vro, wa, wo, xal, xmf, za, zea, zza`.

Many datasets also have large influences from religious materials. An approximate list of wordlists likely to have such influence are: `ace, acm, acq, af, alz, apc, awa, bal, ban, bgz, brx, brx-Beng, brx-Latn, bss, bxm, cce, chm, ee, eo, ewo, ext, ff, fon, fue, fuf, fuq, fur, gl, gqr, grt, gux, gvl, hil, hne, ig, is, kaa, kek, kru, ktb, lad, laj, lhu, lon, lus, mai, mgh, mhy, min, mn, mrj, myv, myx, nan-Latn-TW, nnb, nyo, pag, quc, raj, sba, sck, sd-Deva, seh, sg, sgw, sm, tem, tg, vro, xh, xog, yi, zlm, zne, zu`.

### Wordlists are less effective on highly inflecting languages
Wordlist-based filtering will be less effective for morphologically rich languages, especially agglutinative or polysynthetic languages, where words are built of many smaller units of meaning (morphemes).

### Wordlists are not included for languages with scripts that require segmentation
We don’t include word lists for languages that don’t use spaces, like Myanmar (Burmese). While this is possible, it requires the user to have access to a word segmenter for that language -- and since segmenters vary in their word splitting choices, wordlists are likely of limited utility.


### Why are some words capitalized?
For a given word, we kept the highest-ranked word among differently cased variants. So, for instance, if “Woo” is ranked #4 and “woo” is ranked #16, we keep “Woo” and remove “woo” from the list.


## Pull requests
We did our best to ensure quality, but these lists were automatically selected, and therefore have various issues! If you find issues, feel free to send us a pull request and we’ll look into incorporating your feedback.	

