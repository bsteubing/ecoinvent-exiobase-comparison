# ecoinvent-exiobase-comparison
Comparison of carbon footprint results of the ecoinvent and exiobase

This code was used to do an extensive comparison of carbon footprints (CF) calculated with the ecoinvent 3.4 cutoff and the hybrid version of exiobase (v3.3.18).
The main steps include:

1) A matching of products in ecoinvent to product groups in exiobase, based on a matching of:
- products
- processes (for electricity)
- geographies
- units

2) Comparison of the carbon footprints of matched products, using a number of metrics, e.g.
- correlations
- relative deviation
- coefficient of variation

Specific analysis are included for specific sectors, such as the power sector.

This is followed by a discussion of 
- the sectoral coverage of both databases
- the comparison of CFs
- implications for database improvement
- reasons for differences
- limitations

## Link to the paper
not yet available

## Code and data guide
The code is split into 3 jpuyter notebooks:
1) **00a Matching_article.ipynb**: this notebook does the matching of ecoinvent products with exiobase products (typically representing product groups). 

The notebook builds upon the following **data**:  
* **_ecoinvent metadata_** on products/processes/geographies/units found in the `activity_overview_3.4_cut-off_LCIA_results.xlsx` in `data/ecoinvent`
* _**Exiobase metadata**_ on product groups/geographies/units found in the `hiot_results_PTM_v2.xlsx` in `data/exiobase`
* **_Matching data_** that describes the matching of ecoinvent products, processes and geographies to exiobase equivalents as specified in `Matching file.xlsx` in `data/matching`; additionally this folder contains a matching of ISIC codes to exiobase in the file `ISIC.xlsx`

**Main output:** While the notebook generates a bunch of intermediate files (that can be found in the folder `results/2019-12-02_WW`, e.g. in `matching`), the main output is really `EItoEX_matching_results_HIOT_manual.xlsx` in `results/2019-12-02_WW/matching_results`. This file contains the matched carbon footprint results for all matched products between ecoinvent and exiobaseand useful metadata for filtering and further analysis. Virtually all of the analysis in the following notebooks is based on this file.

2) **00b Analysis_article.ipynb**: this notebook contains basically all analysis presented in the paper. The figures are saved to `results/2019-12-02_WW/figures`.

3) **00c Economic coverage_article.ipynb**: this notebook produces the data for the economic/sectoral coverage of both databases (Table 1 in the article). 

## License
The following licenses apply:
- for the code on this repository: the GNU General Public License Version 3 (see license file)
- for the data produced by the code on this repository: the CC-BY 4.0 license (see license file)
- for the underlying ecoinvent and exiobase data used by the code on this repository: this data is subject to the licenses of the respective databases (see https://ecoinvent.org/ and https://www.exiobase.eu/).
