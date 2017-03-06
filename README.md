# Audio Set Ontology

Dan Ellis dpwe@google.com

v1 2017-03-06

The file [ontology.json](ontology.json) contains the current definition of
the [AudioSet](https://research.google.com/audioset/) ontology, a hierarchical
set of audio event classes.

The json file describes a list of sound entity objects.  Each object contains
the fields:

  * `id`: The machine identifier for this class, a short sequence like
    `/m/0dgw9r`.  Where possible, these are based on Knowledge Graph IDs,
    which were originally used in
    [Freebase](https://en.wikipedia.org/wiki/Freebase).

  * `name`: The Display Name that refers to the class.  Should be unique and
    unambiguous.  Several classes have one or more synonyms included in their
    display names, for example "Male speech, man speaking".

  * `description`: A description of the class in a few lines.

  * `citation_uri`: A pointer to any text used as the basis for the
    description.  Frequently points to a Wikipedia page.

  * `positive_examples`: A list of compact URLs to segments within YouTube files
    that provide confirmed positive examples of this class.  Each entry is of
    the form `youtu.be/8uI9H5jGRV8?start=30&end=40`, meaning the example is the
    10 seconds starting 30 seconds in to the the YouTube video whose ID is
    `8uI9H5jGRV8`.

  * `child_ids`: A list of the `id` fields for any classes that children of this
    class in the class hierarchy.

  * `restrictions`: A list that can include the following values:

    * `abstract` for a class that is principally a container within the
      hierarchy, but will not have any explicit examples for itself. "Human
      voice" is an abstract class.  Abstract classes will always have children.

    * `blacklist` for classes that have been excluded from rating for the time
      being.  These are classes that we found were too difficult for raters to
      mark reliably, or for which we had too much trouble finding candidates, or
      which we decided to drop from labeling for some other reason.

The ontology is made available by Google Inc. under a Creative Commons
Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) license.
