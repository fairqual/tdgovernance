# Plan: tdgovernance (Data Governance Concept template)

This file holds the working plan while the repository is private. It is deleted before the v1.0.0 release so it does not go into the Zenodo archive.

## Open before work continues

- [x] Author list and order set by Lars on 2026-09-30: Franziska Mohr, Mollie Chapman, Leonhard Simon.
- [x] Leonhard Simon's ORCID: 0000-0002-8333-0632.
- [x] Name in the citation is Leonhard Simon, as on the ORCID record (Lars, 2026-09-30).
- [x] Leonhard Simon's affiliation is the Transdisciplinarity Lab, ETH Zurich, as for the other authors (Lars, 2026-09-30).
- [x] Licence is CC BY 4.0, as for the other FAIRqual repositories (Lars, 2026-09-30).
- [x] Spelling mistakes in the DOCX fixed and "Td" used throughout (2026-09-30).
- [ ] Remaining points on the DOCX decided by the authors. In issue #1.

## Context

FAIRqual produced a Data Governance Concept template (DOCX, created by Laura Marqués, last edited by Franziska Mohr on 2026-09-28, no comments, no tracked changes) and the three-phase figure (PDF, one page: Framing, Enacting, Evaluating, each split into researcher and practitioner roles). Both should be public, citable, and archived with a Zenodo DOI in this repository. The repository borrows the documentation files of a washr data package (CITATION.cff, LICENSE.md, NEWS.md, README) but is not an R package. It has no DESCRIPTION, no R/ folder and no pkgdown site. The DOCX also gets a Markdown twin.

Pattern to follow: `fairqual/dataitd24`. Its Zenodo record came from the GitHub integration, and the resource type was fixed by hand on Zenodo afterwards (CITATION.cff says `type: software`, the record says Dataset).

Decisions taken with Lars:

- Name: `tdgovernance`. Zenodo title: "tdgovernance: Data Governance Concept Template for Transdisciplinary Research".
- Authors and order, set by Lars on 2026-09-30: Mohr, Chapman, Simon.
- Shared first authorship: neither CFF 1.2.0 nor Zenodo nor DataCite has a field for it (checked 2026-09-28 against the CFF person keys, CFF issue #363, which is still open, and Zenodo's CFF importer in zenodo-rdm `site/zenodo_rdm/github/schemas.py`). Author order carries the byline. The equal contribution goes into a sentence in CFF `message`, which Zenodo copies into the record's notes, and into the README "How to cite" section.
- The .md mirrors the DOCX exactly. Spelling mistakes are fixed in the DOCX directly (Lars, 2026-09-30). Points that change wording or content go to the authors through issue #1. After any change to the DOCX, the .md is regenerated.
- The repository stays private until the team check, then goes public right before the release (Zenodo only sees public repositories).

## Done so far

- 2026-09-28: Lars created the private repository. First commit on `main` with LICENSE.md (CC BY 4.0, copied from dataitd24) and .gitignore. `dev` created with this plan.
- 2026-09-30: Phase A done on `dev`: both source files copied and renamed, Markdown template, PNG, CITATION.cff, README.md, NEWS.md, committed and pushed. Six spelling fixes made in the DOCX (listed in issue #1), with only `word/document.xml` changed inside the file, and the .md regenerated from the corrected DOCX. Text match between DOCX and .md is empty, and `cffr::cff_validate()` passes. Remaining points are in issue #1. Franziska and Mollie have no GitHub usernames yet, so the collaborator invitations are open.

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
4. CITATION.cff, hand-written in the dataitd24 shape: `cff-version 1.2.0`, `type: software` (CFF only allows software or dataset, so the Zenodo type is fixed by hand later), `license: CC-BY-4.0`, `version: 1.0.0`, abstract from the template's "How to use" text, keywords (data governance, transdisciplinary research, qualitative data, FAIR, research data management, template), `repository-code`, `url`. Authors: Mohr (ORCID 0000-0002-8323-7032, TdLab ETH Zurich), Chapman (ORCID 0000-0003-1399-2144, TdLab ETH Zurich), Simon (ORCID 0000-0002-8333-0632, TdLab ETH Zurich). Emails only for the contact entry, Mollie Chapman (project contact on the org profile since 2026-09-17). If first authorship is shared, `message` reads for example: "If you use this template, please cite it using the metadata below. Franziska Mohr and Leonhard Simon contributed equally and share first authorship."
5. README.md in plain writing: what the concept is and why it exists (from the template's own "How to use" text), the figure, the three phases, the files with download links, how to use the DOCX and the .md, how to cite (DOI added after release), licence, funding (ORD Program of the ETH Board), contact, link to the website.
6. NEWS.md: `# tdgovernance 1.0.0` with one entry for the first release.
7. Keep this plan up to date as items close.
8. Commit on `dev` (no prompts/ archive, since everything in the repository goes into the Zenodo archive), push `dev`.
9. Issue #1 "Open points on the template DOCX before v1.0.0" holds the points that are left. Add Franziska and Mollie as collaborators once they have GitHub usernames.

## Phase B: after issue #1 is closed

1. Delete PLAN.md.
2. If the DOCX changed, regenerate the .md with the same pandoc call.
3. Add `date-released` to CITATION.cff. Keep the citation in the README "How to cite" section in line with CITATION.cff.
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
