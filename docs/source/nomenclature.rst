.. role:: opt

Nomenclature
!!!!!!!!!!!!
The following nomenclature may be used for the description of both :ref:`regulatory-fusions` and :ref:`chimeric-fusions`
in the context of :ref:`categorical-fusions` or :ref:`assayed-fusions` as applicable. The nomenclature components are
organized into three categories: :ref:`gene-components`, :ref:`transcript-components`, and
:ref:`regulatory-components`. These may be used interchangeably, in accordance with the below :ref:`general-rules`.

.. _general-rules:

General Rules
@@@@@@@@@@@@@
1. All components are joined together by the double-colon (``::``) operator. Additional rules apply for sub-components of
   :ref:`regulatory-components`.
#. When describing :ref:`chimeric-fusions`, structural components are ordered in 5' to 3' orientation with respect
   to the transcribed gene product.
#. When describing :ref:`regulatory-fusions`, the regulatory element is indicated first (e.g. reg_e\@IGH::MYC).
#. When describing :ref:`chimeric-fusions` by :ref:`junction-components` (in lieu of full
   :ref:`Transcript Segment Components <transcript-segment-component>`), the 5' fusion partner junction must be the first component, and the 3' fusion
   partner junction must be the last component.
#. Throughout the nomenclature components, some information may be provided optionally. In these cases, the optional
   text is :opt:`colored orange` and may be omitted.


.. _gene-components:

Gene Components
@@@@@@@@@@@@@@@
Gene components are used in coarse representation of gene fusions by constituent gene partners, and are
generally aligned with previous recommendations on gene-gene fusion nomenclature as provided by HGNC [Bruford2021]_.
The most common of these is the :ref:`specific-gene-component`, which is complemented by the
:ref:`multiple-gene-component` (for :ref:`categorical-fusions`) and the :ref:`unknown-gene-component`
(for :ref:`assayed-fusions`).

.. _specific-gene-component:

Specific Gene Component
#######################
The nomenclature for a specific gene is as follows:

   - *First use of a gene in a document*: <Gene Symbol>(<Gene ID>)
   - *Subsequent use in a document*: <Gene Symbol>\ :opt:`(<Gene ID>)`

An example fusion using two Specific Gene Components:

   ``BCR(hgnc:1014)::ABL1(hgnc:76)``

.. _unknown-gene-component:

Unknown Gene Component
######################
The nomenclature for an unknown (typically inferred) gene component (used for :ref:`assayed-fusions`) is a ``?``.

An example fusion using an unknown gene component may be inferred from an ALK break-apart assay:

   ``?::ALK(hgnc:427)``

.. _multiple-gene-component:

Multiple Possible Gene Component
################################
The nomenclature for a multiple possible gene component (used for :ref:`categorical-fusions`) is a ``v``.

An example fusion using a multiple possible gene component is the "ALK Fusions" concept as seen in biomedical
knowledgebases (e.g. `CIViC ALK Fusion`_, `OncoKB ALK Fusions`_):

   ``v::ALK(hgnc:427)``

.. _CIViC ALK Fusion: https://civicdb.org/variants/499/summary
.. _OncoKB ALK Fusions: https://www.oncokb.org/gene/ALK/Fusions

.. _transcript-components:

Transcript Sequence Components
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Transcript sequence components are used in precise representation of gene fusions by sequence representations, and
are designed for compatibility with the HUGO Gene Variation Society `(HGVS) variant nomenclature`_.
Primary among these components is the  :ref:`transcript-segment-component`, and the closely-related
5-prime and 3-prime :ref:`junction-components`.
Additional components are used to represent intervening sequences, provided as a stand-alone literal sequence
(:ref:`linker-sequence-component`) or as a sequence derived from a :ref:`genomic-location`
(:ref:`templated-component`).

.. _(HGVS) variant nomenclature: https://varnomen.hgvs.org/

.. _transcript-segment-component:

Transcript Segment Component
############################
The Transcript Segment Component explicitly describes a segment transcript sequence by start and end exons, and is
represented using the following nomenclature:

   - <Transcript ID>\ :opt:`(<Gene Symbol>)`:e.<start exon>\ :opt:`<+/- offset>`_<end exon>\ :opt:`<+/- offset>`

Offsets, if omitted, indicate that there is no offset from the segment boundary (which is often the case in gene
fusions). For a full description on the use of exon coordinates and offsets, see :ref:`structural-elements`.

Transcript segment components would be used, for example, to represent COSMIC Fusion 165 (`COSF165`_)
under this nomenclature:

   ``ENST00000397938.6(EWSR1):e.1_7::ENST00000527786.6(FLI1):e.6_9``

.. _COSF165: https://cancer.sanger.ac.uk/cosmic/fusion/summary?id=165

.. _junction-components:

Junction Components
###################
The 5-prime and 3-prime Junction Components represent only 5-prime and 3-prime junction locations,
respectively, for :ref:`chimeric-fusions`. These components contrast with the :ref:`transcript-segment-component`
which represents a full segment. As noted in the :ref:`general-rules`, these components must be used only as the
beginning or ending components, respectively, for a fusion.

The nomenclature for these components follows:

   - *5-prime Junction Component*: <Transcript ID>\ :opt:`(<Gene Symbol>)`:e.<end exon>\ :opt:`<+/- offset>`
   - *3-prime Junction Component*: <Transcript ID>\ :opt:`(<Gene Symbol>)`:e.<start exon>\ :opt:`<+/- offset>`

Optional use of offsets have the same meaning as in the :ref:`transcript-segment-component`.

.. _linker-sequence-component:

Linker Sequence Component
#########################
The Linker Sequence Component is represented literally by DNA characters (``A``, ``C``, ``G``, ``T``).

Linker Sequence Components would be used, for example, to represent COSMIC Fusion 1780 (`COSF1780`_)
under this nomenclature:


   - Using :ref:`transcript-segment-component`: ``ENST00000305877.12(BCR):e.1_2::ACTAAAGCG::ENST00000318560.5(ABL1):e.2_11``
   - Using :ref:`junction-components`: ``ENST00000305877.12(BCR):e.2::ACTAAAGCG::ENST00000318560.5(ABL1):e.2``

.. _COSF1780: https://cancer.sanger.ac.uk/cosmic/fusion/summary?id=1780

.. _templated-component:

Templated Linker Sequence Component
###################################
The Templated Linker Sequence Component is represented by a genomic location and strand using the following
nomenclature:

   - <Chromosome ID>\ :opt:`(chr <1-22, X, Y>)`:g.<start coordinate>_<end coordinate>(+/-)

.. _regulatory-components:

Regulatory Components
@@@@@@@@@@@@@@@@@@@@@

.. todo:: transfer the regulatory nomenclature recommendations from this graphic:
   https://lucid.app/lucidspark/7660461e-641b-47b3-8fa3-6576800118d6/edit?invitationId=inv_0f2dd966-edfc-4533-8c15-909f0ee77426

.. [Bruford2021] Bruford EA, et al., HUGO Gene Nomenclature Committee (HGNC) recommendations for the designation of gene fusions. *Leukemia* (October 2021). `doi:10.1038/s41375-021-01436-6 <https://doi.org/10.1038/s41375-021-01436-6>`_
