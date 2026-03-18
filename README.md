# RFCScope

This is the artifact for _RFCScope: Detecting Logical Ambiguities in Internet Protocol Specifications_, published in **ASE 2025**.

[Paper](https://ieeexplore.ieee.org/document/11334266). [Video](http://mrigank.in/RFCScope-video). [Poster](https://mrigank.in/media/ASE2025Poster.pdf). [Slides](https://mrigank.in/media/ASE2025Slides.pdf).

## This repository

### Observations from study of RFC Errata

The `studied-errata/` directory contains the errata considered in our study. The directory has the following structure.

- `I-1/`: Contains the errata from the **Direct inconsistency** category (119 items).
- `I-2/`: Contains the errata from the **Indirect inconsistency** category (70 items).
- `I-3/`: Contains the errata from the **Inconsistency with common knowledge** category (13 items).
- `U-1/`: Contains the errata from the **Direct under-specification (undefined terms)** category (7 items).
- `U-2/`: Contains the errata from the **Direct under-specification (incomplete constraints)** category (15 items).
- `U-3/`: Contains the errata from the **Indirect under-specification** category (10 items).
- `U-4/`: Contains the errata from the **Incorrect/missing references** category (5 items).

We have omitted errata from the **Other** category in this artifact. Each subdirectory contains files named as `Errata<errata-id>-RFC<rfc-number>.md`. Each file contains the original text of the erratum, details of the RFC, a link to the original errata report on the IETF Errata portal, and an explanation of the erratum added by us. The errata belong to the Standards Track RFCs published from January, 2014 to January, 2025.

### LLM prompts used in RFCScope

The `prompts/` directory contains the prompts used in RFCScope for the analysis of RFCs. This directory has the following structure.

- `system-prompts/`: Contains the system prompts used in RFCScope.
  - `inconsistency/`: Contains the system prompts for the inconsistency analysis.
    - `analyzer.md`: The system prompt for the analyzer.
    - `evaluator.md`: The system prompt for the evaluator.
  - `under-specification/`: Contains the system prompts for the under-specification analysis.
    - `analyzer.md`: The system prompt for the analyzer.
    - `evaluator.md`: The system prompt for the evaluator.
- `user-prompts/`: Contains the user prompts used in RFCScope. The user prompts are templates that are filled with the inputs as indicated in the file.
  - `analyzer.md`: The user prompt for the analyzer.
  - `evaluator.md`: The user prompt for the evaluator.

### Bugs detected by RFCScope

The `detected-bugs/` directory contains the bugs selected after manual inspection of the results from RFCScope. The directory contains a file for each detected bug. The files are named as `RFC<number>-<id>.md` when there are multiple bugs for the same RFC, or as `RFC<number>.md` when there is only one bug for the RFC. In total, there are 31 bugs detected across 14 RFCs. Each file in this directory contains the bug report, its categorization, and its confirmation status. The following statuses have been used:

- **Pending**: We have not yet reached out to the RFC authors regarding the bug.
- **Awaiting response from authors**: We have reached out to the RFC authors regarding the bug and are awaiting their response.
- **Confirmed by authors**: We received a response from the RFC authors confirming the bug.
- **Verified on the IETF Errata portal**: The bug has been confirmed by the RFC authors, and is now submitted and verified on the IETF Errata portal.

### Implementation of RFCScope

The `RFCScope/` directory contains our implementation of the _RFCScope_ tool. Please head over to that directory for instructions on running the tool.

## Citing this work

```bibtex
@inproceedings{rfcscope,
  author={Pawagi, Mrigank and Shao, Lize and Lee, Hyeonmin and Sun, Yixin and Wang, Wenxi},
  booktitle={2025 40th IEEE/ACM International Conference on Automated Software Engineering (ASE)}, 
  title={RFCScope: Detecting Logical Ambiguities in Internet Protocol Specifications}, 
  year={2025},
  doi={10.1109/ASE63991.2025.00106}
}
```
