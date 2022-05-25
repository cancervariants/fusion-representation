Minimum Information Model
!!!!!!!!!!!!!!!!!!!!!!!!!

.. figure:: images/salient-elements.svg

   The minimal information for characterizing gene fusions is context-dependent, with components necessary for representing assayed fusions (blue-green boxes), categorical fusions (yellow boxes), or both (white boxes). **(A)** Structural Elements represent the expressed gene product, and are typically characterized at the gene level or the transcript level. Segments of transcripts should be represented by a transcript ID and associated 5’ and/or 3’ exon boundaries. **(B)** Exon Boundaries are characterized by the exon number and offset from the corresponding 5’ or 3’ end. Boundaries also include an aligned Genomic Coordinate with a versioned reference sequence identifier (e.g. a RefSeq NC\_ chromosome sequence accession) and position for data fidelity. Importantly, boundary Genomic Coordinates represent aligned Exon Boundary position, and NOT breakpoints for an associated rearrangement. **(C)** Regulatory Elements are represented minimally by the associated gene and information characterizing the regulatory element class (e.g. enhancer, promoter, or other `INSDC regulatory class`_). If the specific regulatory element is known, the identifier for the regulatory element (e.g. RefSeq NG\_ accession) and associated genomic coordinates should also be provided. **(D)** Categorical fusions are additionally described by functional domains gained or lost by a fusion partner that are critical to fusion transcript activity, as well as if the fusion transcript reading frame should be preserved. **(E)** Assayed fusions are additionally described by the underlying causative event (if known) driving a fusion, as well as details about the molecular assay and whether the fusion was directly observed or inferred. The Evidence and Conclusion Ontology (ECO) provides a standardized set of terms for describing types of assays.

.. _common-elements:

Common Elements
@@@@@@@@@@@@@@@

Some entities are common elements (e.g. :ref:`genes <gene-element>`): complex entities with their own information model and  reused across multiple sections of the gene fusion information model. The information models for those elements are described here.

.. _gene-element:

Gene
####

A gene is defined by a gene symbol and stable gene identifier. For describing gene fusions in humans, we recommend using HUGO Gene Nomenclature Committee (HGNC) genes.

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto

   * - Field
     - Limits
     - Description
   * - Gene symbol
     - 1..1
     - A registered symbol for a gene, e.g. ``ABL1``.
   * - Gene identifier
     - 1..1
     - A registered identifier for a gene, e.g. ``hgnc:76``.

.. _genomic-location:

Genomic Location
################

A genomic location is defined by a chromosomal reference sequence, a start coordinate, and an end coordinate.
Reference sequences should be versioned and associated with a genome assembly. In gene fusions, these are often used to
represent the inter-residue location at which a fusion junction occurs. They may also be used to specify the location of
regulatory elements or templated linker sequence.

.. note:: The coordinates indicated here are not described inherently as residue or inter-residue, 0-based or 1-based.
          Omission on this point is intentional, see the `associated Discussion at GitHub
          <https://github.com/cancervariants/fusions/discussions/17>`_.

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto

   * - Field
     - Limits
     - Description
   * - Reference sequence identifier
     - 1..1
     - A registered identifier for the reference sequence, e.g. ``NC_000001.11`` for chr1 on GRCh38.p14.
   * - Start coordinate
     - 1..1
     - A coordinate representing the start of a genomic location.
   * - End coordinate
     - 1..1
     - A coordinate representing the end of a genomic location.

.. _structural-elements:

Structural Elements
@@@@@@@@@@@@@@@@@@@

The structural elements of a gene fusion represent the expressed gene product, and are typically characterized at the gene
level or the transcript level. :ref:`chimeric-fusions` must be represented by at least two structural elements, and
:ref:`regulatory-fusions` must be represented by at least one structural element and one :ref:`regulatory-element`.

The order of structural elements is important, and by convention representations of structural components for gene
fusions follow a 5' -> 3' ordering. If describing a regulatory fusion, the regulatory element is listed first.

Gene
####

A gene (see the :ref:`gene-element` common element above for information model) may be used as a structural element, in
which case it refers to an unspecified transcript of that gene. For :ref:`categorical-fusions`, this means any
transcript meeting other parameters of the specified fusion. For :ref:`assayed-fusions`, this means that the exact
transcript is not known.

.. _transcript-segment-element:

Transcript segment
##################

A transcript segment is a representation of a transcribed sequence denoted by a 5-prime and 3-prime exon boundary.
Typically, transcript segments are used when the gene fusion junction boundary is known or when representing full-length
:ref:`chimeric-fusions`. In the case where only the fusion junction is reported, only one boundary of a given transcript
segment will be represented.

We recommend that *representative* transcript sequences, when needed, are preferentially selected using the following
criteria:
1. A compatible transcript from MANE Select
2. A compatible transcript from MANE Plus Clinical
3. The longest compatible transcript cDNA sequence
4. The first-published transcript among those transcripts meeting criterion #3

.. todo:: We will add a link to a web-based lookup tool for transcript selection using the
          `UTA Tools <https://github.com/GenomicMedLab/uta-tools>`_ library.

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto

   * - Field
     - Limits
     - Description
   * - Transcript sequence identifier
     - 1..1
     - A registered identifier for the reference transcript sequence, e.g. ``NM_005157.6`` as a MANE Select transcript
       identifier for the ABL1 gene.
   * - 5' exon boundary
     - 0..1
     - A :ref:`boundary` representing the 5-prime end of the transcript segment
   * - 3' exon boundary
     - 0..1
     - A :ref:`boundary` representing the 3-prime end of the transcript segment

.. _boundary:

Segment Boundary
$$$$$$$$$$$$$$$$

A segment boundary describes the exon-anchored coordinate (and corresponding genomic coordinate)
defining a boundary of a transcript segment.

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto

   * - Field
     - Limits
     - Description
   * - Exon number
     - 1..1
     - The exon number from the 5-prime end of the transcript
   * - Exon offset
     - 1..1
     - A value representing the offset from the exon boundary, with positive values offset
       towards the 5-prime end of the transcript and negative values offset towards the 3-prime
       end of the transcript. Offsets can reference sequence in the intronic space.
   * - Genomic location
     - 1..1
     - A :ref:`genomic-location` aligned to the transcript segment boundary.

.. _linker-sequence:

Linker Sequence
###############

A linker sequence is an observed sequence in the gene fusion that typically occurs between
transcript segments, and where the sequence origin is unknown or ambiguous. In cases where
the linker sequence is a known intronic or intergenic region, it should be represented as a
:ref:`templated-linker` instead.

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto

   * - Field
     - Limits
     - Description
   * - Sequence
     - 1..1
     - A literal sequence expressed as cDNA.

.. _templated-linker:

Templated Linker Sequence
#########################

A templated linker sequence is an observed sequence in the gene fusion that typically occurs
between transcript segments, and where the sequence origin is a known intronic or intergenic region.

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto

   * - Field
     - Limits
     - Description
   * - Genomic location
     - 1..1
     - A :ref:`genomic-location` from which the templated linker sequence is derived.
   * - Sequence
     - 0..1
     - An optional literal sequence derived from the genomic location.

.. todo:: regulatory elements, categorical elements, assayed elements