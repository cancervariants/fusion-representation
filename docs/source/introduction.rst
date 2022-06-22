Introduction
!!!!!!!!!!!!

Maximizing the research and clinical value of genomic information will require
that clinicians, researchers, and testing laboratories capture and report genetic variation data reliably.
The Gene Fusion Guidelines — written by a partnership among experts from clinical laboratory testing and informatics
societies — is an open set of guidelines to standardize the representation of gene fusion data and knowledge.

Here we document the primary contributions of this specification for variation representation:

* **Terminology.** We provide definitions for gene fusions and disambiguate several classes, including
  chimeric product and regulatory fusions, from related but distinct concepts such as genomic rearrangements.
  We also elaborate on the distinction between gene fusions represented as aggregated concepts in cohort studies and
  biomedical knowledgebases from individual fusions observed in a sample.
* **Minimum information model.** We provide recommendations on the salient data elements for the representation of
  assayed and categorical gene fusions. These data elements capture key information used in the evaluation of
  gene fusions in clinical applications and biomedical research.
* **Human-readable nomenclature.** We provide recommendations for a human-readable nomenclature for the designation of
  gene fusions and associated regulatory elements, at the sequence or gene level.
* **Gene fusion information capture workflows.** We provide recommendations for gathering information about
  gene fusions in bioinformatics pipelines and knowledge curation efforts.
* **Supporting tools.** We provide a Python library (fusor) that enforces data objects containing the salient elements
  of gene fusions, for use in informatics pipelines. We also provide an educational web tool (fusion-curation) that
  implements our recommendations to train gene fusion curators.

.. todo:: For a discussion of the Gene Fusion Guidelines with respect to existing standards, see :ref:`relationships`.
