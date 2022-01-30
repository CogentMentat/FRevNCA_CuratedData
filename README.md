# FRevNCA_CuratedData

Curated and augmented legislative speech data from the National Constituent Assembly during the French Revolution.  Companion to PNAS article [Individuals, institutions, and innovation in the debates of the French Revolution](https://www.pnas.org/content/115/18/4607.short).

## Files

## Column guide:

* `NCASpeechId`: universal speech index used for all data.
* `Date`: date of the speech.  These were cleaned and corrected from the original, which had errors in order and in formatting.
* `OrigFile`: original xml file.
* `Volume`: original volume of the Archives Parlementaires (AP).
* `PbTagId`: location id used throughout the original xml, useful for old FRDA web interface or working with original xml files.  The speech falls after this PbTagId and before the next, in AP page order.
* `PageNum`: page of the AP on which the speech occurs.
* `SpeakerStr`: speaker string provided by the FRDA xml
* `Surname` and `Name`: identities disambiguated from all the SpeakerStrs.  These are the ones used in the PNAS analysis.  Note: although a lot of manual attention produced these attributions, they are not guaranteed 100% accurate!  There was significant noise in the SpeakerStr data - see the [Supplementary Material](https://www.pnas.org/content/suppl/2018/04/16/1717729115.DCSupplemental), "Preparing and characterizing speech data", for more detail. "nomatch" indicates the speech's `SpeakerStr` was not assigned to a disambiguated entity.
* `Affiliation`: "g" (gauche), "d" (droite), "nonpos" (matched identity isn't positively identified as gauche or droite according to our historian co-author), or "nomatch" (no identity match was made to `SpeakerStr`
* `Estate`, 1st/2nd/3rd estate, or "nonpos"/"nomatch" as for `Affiliation`.
* `Club`: an assortment of political clubs to which individuals belonged, or "nonpos"/"nomatch".
* `President`: binary presidential speech indicator.
* `CommitteeStatus`: "newitem" (speaker as committee proxy introduces a decree proposal to the floor), "indebate" (committee proxy speaks in the midst of debate), or "noncomm" (speaker is not a committee proxy).
* `RawTextFr`: The raw speech text obtained from the original xml.
* `RawTextEnTrans`: For giggles, I made a script circa ~2016 that queries Google Translate with all of the raw speeches.  Results are included here.
* `ProcessedText`: `RawTextFr` after light tokenization.
* `ProcessedVocabText`: `ProcessedText` after removing words with fewer than 3 characters, stop words, then limiting to a 10,000-word vocabulary by highest observed frequency.

## Notebooks

## Requirements (versions used)

* python (3.7.10)
* numpy (1.18.5)
* pandas (1.3.5)
