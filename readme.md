# How does SNSF research relate to the UN Sustainable Development Goals?

**The SNSF performed an exploratory analysis to determine the extent to which the projects it funds are related to the UN Sustainable Development Goals. The analysis found evidence of links to the Goals in all research areas. A survey of researchers is set to provide further insights.**

[English](https://data.snf.ch/stories/snf-research-and-sdgs-en.html)\
[German](https://data.snf.ch/stories/snf-forschung-und-nachhaltigkeitszielen-de.html)\
[French](https://data.snf.ch/stories/recherche-du-fns-et-odd-fr.html)

**Author(s)**: Stéphanie Würth, Sarah Achermann, and Simon Gorin

**Publication date**: 13.04.2023

### Data description

The data used in this data story are available in the folder `data`. There are 5 datasets available as `.RData` files: `sdg_mentions_all.RData`, `data_sdgs.RData`, `data_sdg07_disciplines.RData`, `data_sdg07_collaborations.RData`, and `data_grants_w_sdg.RData`(see below for a description of each dataset). These files can be read in`R`with the function`load()`. For convenience, the files are also available in a`.csv`format for non-R users (see the`data/csv` folder).

#### Data set 1: sdg_mentions_all

This dataset contains summary statistics on the 12431 grants (accepted proposals) analysed. Each row corresponds to one of the 17 SDGs. Here is a description of the variables:

-   `sdg_result`: name of the SDG in English.

-   `n_dim`: the number of grants associated with at least one SDG (Dimensions classifier).

-   `freq_dim`: the frequency (proportion) of grants associated with at least one SDG (Dimensions classifier).

-   `n_elsevier`: the number of grants associated with at least one SDG (Elsevier classifier).

-   `freq_elsevier`: the frequency (proportion) of grants associated with at least one SDG (Elsevier classifier).

-   `n_both`: the number of grants associated with at least one SDG by both classifiers (Elsevier and Dimensions).

-   `freq_both`: the frequency (proportion) of grants associated with at least one SDG by both classifiers (Elsevier and Dimensions).

-   `sdg_result_de`: name of the SDG in German.

-   `sdg_result_fr`: name of the SDG in French.

#### Data set 2: data_sdgs

This dataset contains information on the 1489 grants associated with at least one SDG out of the 12431 grants (accepted proposals) analysed. As described in the data story, a grant was associated with an SDG only if both classifiers indicated the same SDG. In addition, because the classifiers could associate more than one SDG to the same grant, the data set contains more rows than the actual number of grants. Here is a description of the variables:

-   `Number`: Unique identifier of the grant (can be used to search grant at <https://data.snf.ch/grants>).

-   `sdg_result`: The number of the associated SDG.

-   `FundingInstrumentGaReporting`: Mid-level funding scheme hierarchy.

-   `CallDecisionYear`: The year in which decisions on most grants of a call are made. It normally means the year in which a grant was approved.

-   `ResearchInstitutionType`: This is the institution type of the co-applicant (Cantonal Universities, ETH Domain, Universities of Applied Sciences [UAS], Universities of Teacher Education [UTE], Other Research Institutions).

-   `MainDiscipline`: Name of the discipline. Only the main discipline. The responsible applicant chooses the most suitable discipline for the application, from a [list of disciplines supplied by the SNSF](https://www.snf.ch/SiteCollectionDocuments/allg_disziplinenliste.pdf).

-   `MainDisciplineLevel2`: Mid level of MainDiscipline.

-   `FundingInstrumentGaLevel1`: Highest hierarchical level of the [funding schemes](https://data.snf.ch/about/glossary#funding_instrument), consisting of the following five groups (Careers, Infrastructure, Programmes, Project funding, and Science communication).

-   `AmountGranted`: The amount approved to the grant.

-   `IsApproved`: Whether the proposal has been approved. Only approved grants (variable is `TRUE`) are present in this dataset.

-   `Title`: Name of the grant.

-   `Keywords`: The top five keywords of the grant in the order entered by the responsible applicant.

-   `Abstract`: A scientific abstract of the grant.

-   `n_applicants`: The number of applicants.

-   `is_collaborative`: Whether the grant was considered as collaborative (`1`) or not (`0`).

-   `is_collaborative_cat`: Same as `is_collaborative` but coded with categories (`Collaborative` maps to `1`) or not (`Non-collaborative` maps to `0`).

-   `n_disciplines`: The number of disciplines related to the grant.

-   `is_interdisciplinary`: Whether the grant was considered as interdisciplinary (`1`) or not (`0`).

-   `is_interdisciplinary_cat`: Same as `is_collaborative` but coded with categories (`More than one discipline` maps to `1`) or not (`One discipline` maps to `0`).

-   `is_collaborative_cat_de`: German version of `is_collaborative_cat`.

-   `"is_collaborative_cat_fr`: French version of `is_collaborative_cat`.

-   `is_interdisciplinary_cat_de`: German version of `is_interdisciplinary_cat`.

-   `is_interdisciplinary_cat_fr`: French version of `is_interdisciplinary_cat`.

-   `MainDisciplineLevel1`: The three major research domains that the SNSF distinguishes: humanities and social sciences (SSH); mathematics, natural and engineering sciences (MINT); biology and medicine (LS).

-   `MainDisciplineLevel1_de`: German version of `MainDisciplineLevel1`.

-   `MainDisciplineLevel1_fr`: French version of `MainDisciplineLevel1`.

#### Data set 3: data_sdg07_disciplines

This dataset is similar to the second dataset (`data_sdgs`), with the difference that it only contains grants associated with SDG 7 (affordable and clean energy) and associated with more than one discipline. Additional variables are also included. Here is a description of the variables (*please note that only variables that are not already present in `data_sdgs` are described*):

-   `disc1`: Number of the first secondary disciplines chooses by the responsible applicant from a [list of disciplines supplied by the SNSF](https://www.snf.ch/SiteCollectionDocuments/allg_disziplinenliste.pdf).

-   `disc2`: Number of the second secondary disciplines chooses by the responsible applicant from a [list of disciplines supplied by the SNSF](https://www.snf.ch/SiteCollectionDocuments/allg_disziplinenliste.pdf).

-   `disc3`: Number of the third secondary disciplines chooses by the responsible applicant from a [list of disciplines supplied by the SNSF](https://www.snf.ch/SiteCollectionDocuments/allg_disziplinenliste.pdf).

-   `disc4`: Number of the fourth secondary disciplines chooses by the responsible applicant from a [list of disciplines supplied by the SNSF](https://www.snf.ch/SiteCollectionDocuments/allg_disziplinenliste.pdf).

-   `disc5`: Number of the fifth secondary disciplines chooses by the responsible applicant from a [list of disciplines supplied by the SNSF](https://www.snf.ch/SiteCollectionDocuments/allg_disziplinenliste.pdf).

-   `disc6`: Number of the sixth secondary disciplines chooses by the responsible applicant from a [list of disciplines supplied by the SNSF](https://www.snf.ch/SiteCollectionDocuments/allg_disziplinenliste.pdf).

#### Data set 4: data_sdg07_collaborations

This dataset contains information on the institution of applicants and co-applicants for grants (i.e. only grants involving collaboration are available) associated with SDG 7 (clean and affordable energy). Each row represents a researcher (applicant or co-applicant). Note that the variable `Institution1` refers to the institution of the applicant and `Institution2` refers to the institution of the co-applicant. Therefore, when `role` is set to *Applicant*, `Institution1` and `Institution2` are the same, reflecting the institution of the applicant. When `role` is set to *Co-candidates*, `Institution1` refers to the applicant's institution and `Institution2` to the co-applicant's institution. Here follows a description of the variables:

-   `Number`: Unique identifier of the grant (can be used to search grant at <https://data.snf.ch/grants>).

-   `Institution1`: This is the Swiss research institution or university acronym of the applicant.

-   `Institution2`: This is the research institution or university acronym of the co-applicant. In the case of research institutions outside Switzerland, this field say *International*.

-   `IntitutionType1`: This is the institution type of the applicant (Cantonal Universities, ETH Domain, Universities of Applied Sciences [UAS], Universities of Teacher Education [UTE], Other Research Institutions).

-   `IntitutionType2`: This is the institution type of the co-applicant (Cantonal Universities, ETH Domain, Universities of Applied Sciences [UAS], Universities of Teacher Education [UTE], Other Research Institutions). When the co-applicant is from an institution outside Switzerland, this field say `NA`.

-   `Role`: The role of the researcher in the project (applicant or co-applicant).

-   `same_inst_collab`: Whether the project involved a collaboration between researchers from the same institution (`1`) or not (`0`).

#### Data set 5: data_grants_w\_sdg

This dataset is similar to the second dataset (`data_sdgs`), with the difference that here all analysed grants (12431) are included and variables indicating whether the grant is related to an SDG or not have been included. Here is a description of the variables (*please note that only variables that are not already present in `data_sdgs` are described*):

-   `n_sdgs`: The number of SDGs detected by both the two classifiers (Elsevier and Dimensions),

-   `is_sdg`: Whether the grant is associated to any SDG (`SDG reference`) or not (`No SDG reference`).

-   `is_sdg_de`: Same as `is_sdg`, but in German.

-   `is_sdg_fr`: Same as `is_sdg`, but in French.
