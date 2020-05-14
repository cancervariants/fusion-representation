# Minimal Data Elements for Fusions

Gordana comments:
  I fully agree the scope of this manuscript should be on defining
  the genomic event.
  We could still break this into two parts:
    1) specific allele / observation
      a) functional consequences of this allele
      b) what are the elements I want to communicate?
      c) HGVS does not capture the functional consequence of event
    2) fusion variant as a recurrent / categorical variant in cancer
      a) what are the standard elements to keep there?
      b) e.g. for BCR-ABL, what are known breakpoints?
  Let's aim to include members from other organizations early on.
  We should write up proposal / scope document and send around.
  
Dmitriy:
  - Latest HGVS recommendation is good for representation
    - Gordana and Alex agree
  - How to model this in a database for search
  - Not all fusion variants are created equal
    - How do we capture functional impact of a variant?
      - Say somebody detects a fusion (two well-known genes)
      - How do you pick up relevant entries, and ignore irrelevant entries

General agreement on Gordana's ideas above

Allele interpretation problem is not handled yet
Do we want to divide these elements into the minimum elements and
additional data elements

Christian:
We need two parts to this story:
  - Bottom-up: What people in this room do; tease apart all the data
    elements and categorize / roll them up
  - Top-down:  Declare at the beginning what we want to do, at varying
    detail, and why that is useful. Remember that somebody has to do it. 
    What is feasible?

Dmitriy:
  - There are situations where each search (from HGVS representation) we
    could map it nicely to existing knowledge.

Gordana:
  - First question is why are we doing this, how are we helping the
    field? Describing both elements to describe an observation, as well 
    as what should be stored in knowledgebases.
  - We should reach out to CIViC as part of this, see if we can get them
    to collaborate on the development of this.