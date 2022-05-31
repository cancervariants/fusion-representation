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
1. All components are joined together by the double-colon (``::``) operator.
#. When describing :ref:`chimeric-fusions`, structural components are ordered in 5' to 3' orientation with respect
   to the transcribed gene product.
#. When describing :ref:`regulatory-fusions`, the regulatory element is indicated first (e.g. reg_e@IGH::MYC).
#. When describing :ref:`chimeric-fusions` by junctions (in lieu of full ), the 5' fusion partner
   junction must be the first component, and the 3' fusion partner junction must be the last component.
#. Throughout the nomenclature components, some information may be provided optionally. In these cases, the optional
   text is :opt:`colored orange` and may be omitted.


.. _gene-components:

Gene Components
@@@@@@@@@@@@@@@
Gene components are relatively straightforward, and are generally aligned with previous recommendations on gene-gene
fusion nomenclature as provided by HGNC [Bruford2021]_. The most common of these is the :ref:`specific-gene-component`,
which is complemented by the :ref:`multiple-gene-component` (for :ref:`categorical-fusions`) and the
:ref:`unknown-gene-component` (for :ref:`assayed-fusions`).

.. _specific-gene-component:

Specific Gene Component
#######################
The nomenclature for a specific gene (first use in a document) is as follows:

   <Gene Symbol>(<Gene ID>)

The Gene ID is optional after first use within a document:

   <Gene Symbol>\ :opt:`(<Gene ID>)`

An example fusion using two Specific Gene Components:

   BCR(hgnc:1014)::ABL1(hgnc:76)

Unknown Gene Component
######################
The nomenclature for an unknown (typically inferred) gene component (used for :ref:`assayed-fusions`) is a "?".

An example fusion using an unknown gene component may be inferred from an ALK break-apart assay:

   ?::ALK(hgnc:427)

Multiple Possible Gene Component
################################
The nomenclature for a multiple possible gene component (used for :ref:`categorical-fusions`) is a "v".

An example fusion using a multiple possible gene component is the "ALK Fusions" concept as seen in biomedical
knowledgebases (e.g. `CIViC ALK Fusion`_, `OncoKB ALK Fusions`_):

   v::ALK(hgnc:427)

.. _CIViC ALK Fusion: https://civicdb.org/variants/499/summary
.. _OncoKB ALK Fusions: https://www.oncokb.org/gene/ALK/Fusions

.. _transcript-components:

Transcript Components
@@@@@@@@@@@@@@@@@@@@@
lorem impsum

.. _regulatory-components:

Regulatory Components
@@@@@@@@@@@@@@@@@@@@@
lorem impsum

.. todo:: transfer the nomenclature recommendations from this graphic:
   https://lucid.app/lucidspark/7660461e-641b-47b3-8fa3-6576800118d6/edit?invitationId=inv_0f2dd966-edfc-4533-8c15-909f0ee77426

.. [Bruford2021] Bruford EA, et al., HUGO Gene Nomenclature Committee (HGNC) recommendations for the designation of gene fusions. *Leukemia* (October 2021). `doi:10.1038/s41375-021-01436-6 <https://doi.org/10.1038/s41375-021-01436-6>`_
