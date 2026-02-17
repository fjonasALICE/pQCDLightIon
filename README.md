# pQCDLightIon

This repository contains perturbative QCD calculations for light-ion collisions used in the paper:

> **[Paper Title Placeholder]**  
> Author 1, Author 2, et al.  
> *Journal Name*, Volume(Issue), Pages (Year)  
> arXiv:XXXX.XXXXX [hep-ph]

## Citation

If you use this data, please cite:

```bibtex
@article{AuthorYear,
    author = "Author1, First and Author2, Second and others",
    title = "{Paper Title Placeholder}",
    journal = "Journal Name",
    volume = "XXX",
    year = "XXXX",
    pages = "XXX-XXX",
    doi = "XX.XXXX/journal.XXXX",
    eprint = "XXXX.XXXXX",
    archivePrefix = "arXiv",
    primaryClass = "hep-ph"
}
```

## Data Organization

This repository contains theoretical predictions for hadron and photon production in light-ion collisions using two calculation frameworks:

### 1. JETPHOX Calculations ([`jetphox/`](./jetphox/))

Direct photon production calculations including:

- **Observables**: Nuclear modification factors (R_pO, R_OO)
- **Collision energies**: 5.36 TeV, 9.62 TeV
- **Nuclear PDF sets**: 
  - EPPS21
  - nCTEQ15HQ
  - nNNPDF30
  - TUJU21

**File naming convention**: `PromptPhoton_{Observable}_{nPDF}_{Energy}GeV.txt`

**Example files**:
- `PromptPhoton_RpO_EPPS21nlo_9620GeV.txt` - proton-oxygen nuclear modification factor
- `PromptPhoton_ROO_TUJU21_5360GeV.txt` - oxygen-oxygen nuclear modification factor

---

### 2. INCNLO Calculations ([`incnlo/`](./incnlo/))

Hadron production calculations organized into three categories:

#### 2.1 Nuclear Modification Factors ([`incnlo/nuclearmodfactor/`](./incnlo/nuclearmodfactor/))

Nuclear modification factors for π⁰ and charged hadrons:

- **Observables**: R_pO (proton-nucleus), R_OO (nucleus-nucleus)
- **Particle types**: π⁰ (`pi0`), charged hadrons (`chhadron`)
- **Collision energies**: 5.36 TeV, 9.62 TeV
- **Fragmentation function**: BKK

**File naming convention**: `incnlo_{particle}_{Observable}_{pPDF}_{nPDF}_{FF}_{Energy}GeV.txt`

**Example files**:
- `incnlo_pi0_RpO_CT18ANLO_EPPS21nlo_CT18Anlo_O16_BKK_9620GeV.txt`
- `incnlo_chhadron_ROO_EPPS21nlo_CT18Anlo_O16_CT18ANLO_BKK_5360GeV.txt`

#### 2.2 Cross-Section Energy Ratios ([`incnlo/cme_ratios/`](./incnlo/cme_ratios/))

Ratios of production cross-sections at different collision energies:

- **Particle types**: π⁰, charged hadrons
- **Energy ratios**: 
  - 5.36 TeV / 9.62 TeV
  - 7.00 TeV / 9.62 TeV
  - 8.00 TeV / 9.62 TeV
  - 13.0 TeV / 9.62 TeV
  - 13.6 TeV / 9.62 TeV
- **PDF set**: CT18ANLO
- **Fragmentation function**: BKK

**File naming convention**: `incnlo_{particle}_CrossSectionRatio_{PDF}_{PDF}_{FF}_{E1}over{E2}GeV.txt`

**Example files**:
- `incnlo_pi0_CrossSectionRatio_CT18ANLO_CT18ANLO_BKK_13600over9620GeV.txt`
- `incnlo_chhadron_CrossSectionRatio_CT18ANLO_CT18ANLO_BKK_5360over9620GeV.txt`

#### 2.3 Derived Ratios ([`incnlo/derivedratios/`](./incnlo/derivedratios/))

Additional derived quantities from the nuclear modification factors.

---

## Data Format

All data files follow a common tabular format:

```
pt    [observable]    error
7.0   0.9395         0.0220
9.0   0.9518         0.0199
...
```

Where:
- `pt` = transverse momentum (GeV/c)
- `[observable]` = R_pO, R_OO, or cross-section ratio value
- `error` = uncertainty on the observable (either scale or nPDF)

---


## Contact

For questions about this data, please contact [contact information placeholder] or open an issue.