# Plan: tdgovernance (Data Governance Concept template)

This file holds the working plan while the repository is private. It is deleted before the v1.0.0 release so it does not go into the Zenodo archive.

## Open before work continues

- [ ] Author list confirmed (provisional: Franziska Mohr, Leon Simon, Mollie Chapman).
- [ ] Author order confirmed, and whether two people share first authorship.
- [ ] Leon Simon's ORCID and affiliation.
- [ ] Licence confirmed (CC BY 4.0, as for the other FAIRqual repositories).
- [ ] Franziska Mohr has corrected the DOCX (list of corrections below).

## Context

FAIRqual produced a Data Governance Concept template (DOCX, created by Laura Marqués, last edited by Franziska Mohr on 2026-09-28, no comments, no tracked changes) and the three-phase figure (PDF, one page: Framing, Enacting, Evaluating, each split into researcher and practitioner roles). Both should be public, citable, and archived with a Zenodo DOI in this repository. The repository borrows the documentation files of a washr data package (CITATION.cff, LICENSE.md, NEWS.md, README) but is not an R package. It has no DESCRIPTION, no R/ folder and no pkgdown site. The DOCX also gets a Markdown twin.

Pattern to follow: `fairqual/dataitd24`. Its Zenodo record came from the GitHub integration, and the resource type was fixed by hand on Zenodo afterwards (CITATION.cff says `type: software`, the record says Dataset).

Decisions taken with Lars:

- Name: `tdgovernance`. Zenodo title: "tdgovernance: Data Governance Concept Template for Transdisciplinary Research".
- Authors are provisional. Full confirmation (list, order, ORCIDs, shared first authorship) is a release gate.
- Shared first authorship: neither CFF 1.2.0 nor Zenodo nor DataCite has a field for it (checked 2026-09-28 against the CFF person keys, CFF issue #363, which is still open, and Zenodo's CFF importer in zenodo-rdm `site/zenodo_rdm/github/schemas.py`). Author order carries the byline. The equal contribution goes into a sentence in CFF `message`, which Zenodo copies into the record's notes, and into the README "How to cite" section.
- The .md mirrors the DOCX exactly. Errors go to Franziska as a list, she fixes the DOCX, then the .md is regenerated.
- The repository stays private until the team check, then goes public right before the release (Zenodo only sees public repositories).

## Done so far

- 2026-09-28: Lars created the private repository. First commit on `main` with LICENSE.md (CC BY 4.0, copied from dataitd24) and .gitignore. `dev` created with this plan.

## Repository layout

```
tdgovernance/
  README.md
  CITATION.cff
  LICENSE.md          CC BY 4.0
  NEWS.md
  .gitignore
  template/
    data-governance-concept-template.docx   the DOCX, renamed only
    data-governance-concept-template.md     pandoc conversion
  figure/
    data-governance-concept-phases.pdf      the PDF, renamed only
    data-governance-concept-phases.png      rendered from the PDF for the README
```

Source files: `fairqual_template_DGC_27092028_noTC.docx` and `fairqual_data_governance_concept_20260818.pdf`. The date typo in the DOCX file name (2028) disappears with the rename, and the version comes from the release tag.

## Phase A: build the repository (on Lars's word)

1. Copy and rename the two source files.
2. Markdown template with `pandoc -t gfm` from the DOCX (72-column wrap, like dataitd24). Clean only conversion artefacts: remove the `<!-- -->` list breaks in Phase 3, keep italics for guidance text, keep the bold-italic phase labels, keep the text word for word.
3. PNG with `pdftoppm -png -r 200 -singlefile` from the PDF (GitHub cannot show a PDF inline).
4. CITATION.cff, hand-written in the dataitd24 shape: `cff-version 1.2.0`, `type: software` (CFF only allows software or dataset, so the Zenodo type is fixed by hand later), `license: CC-BY-4.0`, `version: 1.0.0`, abstract from the template's "How to use" text, keywords (data governance, transdisciplinary research, qualitative data, FAIR, research data management, template), `repository-code`, `url`. Authors: Mohr (ORCID 0000-0002-8323-7032, TdLab ETH Zurich), Simon (Kintegra, ORCID to collect), Chapman (ORCID 0000-0003-1399-2144, TdLab ETH Zurich). Emails only for the contact entry, Mollie Chapman (project contact on the org profile since 2026-09-17). A comment line marks the author list as unconfirmed. If first authorship is shared, `message` reads for example: "If you use this template, please cite it using the metadata below. Franziska Mohr and Leon Simon contributed equally and share first authorship."
5. README.md in plain writing: what the concept is and why it exists (from the template's own "How to use" text), the figure, the three phases, the files with download links, how to use the DOCX and the .md, how to cite (DOI added after release), licence, funding (ORD Program of the ETH Board), contact, link to the website.
6. NEWS.md: `# tdgovernance 1.0.0` with one entry for the first release.
7. Keep this plan up to date as items close.
8. Commit on `dev` (no prompts/ archive, since everything in the repository goes into the Zenodo archive), push `dev`.
9. Draft a GitHub issue "Corrections to the DOCX before v1.0.0" with the list below. Show it to Lars and create it only after his OK. Add Franziska and Mollie as collaborators.

### DOCX corrections list for Franziska (issue draft content)

1. Abstract: "data government concept" should be "data governance concept".
2. "Td approach" and "In a TD process" (How to use, Phase 2): pick one spelling. The project uses "Td".
3. Phase 1: "Definition of the expected of outcomes" should be "Definition of the expected outcomes".
4. Phase 1: "How will be these skill be put into practice, and how far will trainings be necessary?" could read "How will these skills be put into practice, and to what extent will training be necessary?"
5. The question on who ensures the continuous update of the concept appears in Phase 1 and again in Phase 2 (worded slightly differently). Keep one, or confirm the repeat is on purpose.
6. The question on mechanisms to review and update the concept appears in Phase 1 and again under "Potential revisions". Same choice.
7. Phase 2, last item: question mark missing after "the way data is managed".
8. Potential revisions: "Will there changes" should be "Will there be changes".
9. Potential revisions: the parenthesis opened at "(e.g., do many want to share" is never closed.
10. "Following questions should guide" and "Following questions guide" should start with "The following questions".
11. "Data Governance Concept" and "data governance concept" are both used. Pick one.
12. Phase headings and the figure: the figure calls the phases Framing, Enacting, Evaluating, while the template uses "raising the discussion", "Putting the plan into place", "Re-assessing and next steps". Adding the figure names would tie the two together.
13. Phase 3 bullets are three separate lists in the DOCX (formatting only).
14. Optional: place the figure in the "How to use this template" section.

Work stops here until the authors are confirmed and Franziska has corrected the DOCX.

## Phase B: after the DOCX corrections and the author check

1. Delete PLAN.md.
2. Replace the DOCX with the corrected version and regenerate the .md with the same pandoc call.
3. Update CITATION.cff with the confirmed authors, order, ORCIDs, and the shared first authorship sentence in `message` if it applies. Remove the "unconfirmed" comment.
4. Commit on `dev`, open the pull request from `dev` into `main`, merge.

## Phase C: release (each step on Lars's go-ahead)

1. Make the repository public.
2. Lars switches on `fairqual/tdgovernance` at zenodo.org/account/settings/github.
3. `gh release create v1.0.0` from `main`.
4. On the new Zenodo record, set by hand: resource type (suggest Publication / Project deliverable, since it is a FAIRqual output), funding (ORD Program of the ETH Board), related identifier to the GitHub repository. Check the author order and that the equal-contribution note arrived from `message`.
5. Add the concept DOI to CITATION.cff (`doi:`) and a DOI badge to README.md on `dev`, pull request, merge. No new release needed, because the concept DOI resolves to the latest version.
6. Sync `dev` with `main` and push `origin/dev`.
7. Add the repository to the list in `fairqual/.github` `profile/README.md`, through its `dev` branch and a pull request.

## Verification

- Text match: `pandoc -t plain` of the DOCX and of the .md, whitespace normalised, then `diff`. The diff must be empty (repeat after Phase B).
- CITATION.cff: `Rscript -e 'cffr::cff_validate("CITATION.cff")'`.
- README: open the repository on GitHub and check that the figure shows and the download links work.
- After release: `curl -s https://zenodo.org/api/records/<id>` to check creators, licence, resource type and files (DOCX, MD, PDF, PNG). Check that the DOI resolves and that GitHub shows "Cite this repository".
