![Version](https://img.shields.io/github/v/release/DCMLab/pleyel_quartets?display_name=tag)
[![DOI](https://zenodo.org/badge/{{ zenodo_badge_id }}.svg)](https://doi.org/{{ concept_doi }})
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/pleyel_quartets)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/pleyel_quartets](https://github.com/DCMLab/pleyel_quartets) and the corresponding
* documentation page [https://dcmlab.github.io/pleyel_quartets](https://dcmlab.github.io/pleyel_quartets)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/pleyel_quartets/introduction).

# Ignaz Pleyel – String Quartets (A corpus of annotated scores)

In his own time, Ignaz Pleyel's fame may have surpassed that of Mozart or Haydn. Today, his music is rarely performed,
though the piano manufacturer he founded, Pleyel & Cie., survives to this day. These two string quartets are quite early
works, completed before the composer left Austria for Alsace and truly launched his career. While Pleyel's mature works
gained a reputation (perhaps unearned) for being simple and didactic, these Quartets engage in their own share of
instrumental pyrotechnics. Our annotations for these works illustrate what is arguably the ideal archetypical Classical
style and have proven useful in establishing an analytical paradigm for our research efforts.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/pleyel_quartets/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [pleyel_quartets.zip](https://github.com/DCMLab/pleyel_quartets/releases/latest/download/pleyel_quartets.zip)
  * [pleyel_quartets.datapackage.json](https://github.com/DCMLab/pleyel_quartets/releases/latest/download/pleyel_quartets.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/pleyel_quartets.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first movement of the first quartet, Op. 2, No. 1, B.307 has the following files:

* `MS3/b307op2n1a.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/b307op2n1a.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/b307op2n1a.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/b307op2n1a.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/b307op2n1a.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/b307op2n1a.harmonies.tsv")
notes = ms3.load_tsv("notes/b307op2n1a.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/pleyel_quartets/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/pleyel_quartets/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Ignaz Pleyel – String Quartets (A corpus of annotated scores) [Data set]. Zenodo. https://doi.org/{{ concept_doi }}

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## File naming convention

```regex
b(?<benton>\d{3})
op(?<op>\d)
n(?<no>\d)
(?<movement>a|b|c)
```

## Overview
|file_name |measures|labels|standard|                annotators                 |reviewers|
|----------|-------:|-----:|--------|-------------------------------------------|---------|
|b307op2n1a|     197|   402|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, AN   |
|b307op2n1b|     107|   190|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, AN   |
|b307op2n1c|      78|   156|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, AN   |
|b309op2n3a|      98|   189|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, AN   |
|b309op2n3b|     269|   507|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK, AN   |
|b309op2n3c|      74|   123|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK       |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
