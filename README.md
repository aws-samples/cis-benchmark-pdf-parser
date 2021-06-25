# cis_pdf_parser.py

cis_pdf_parser.py is a python script for parsing CIS Benchmark PDF files from the [Center for Internet Security](https://www.cisecurity.org/cis-benchmarks/) into a CSV file format. As of June 2021, all benchmarks are only published in PDF format, which limits their usability. A CSV format can prove more useful for various industry use cases.

## Setup

cis_pdf_parser.py is dependent upon python3, the fitz, csv, re, logging, and argparse modules, and the script expects a path to a CIS Benchmark .pdf file and a filename to output to.

Run the following:
```
$ pip install -r requirements.txt
```

## Usage

```
$ python3 cis_pdf_parser.py -h
usage: cis_pdf_parser.py [-h] [--pdf_file PDF_FILE] [--out_file OUT_FILE]

Parses CIS Benchmark PDF content into CSV Format

optional arguments:
  -h, --help           show this help message and exit

required arguments:
  --pdf_file PDF_FILE  PDF File to Parse
  --out_file OUT_FILE  Output file in .csv format
```

## Full Command Example:

```
$ python3 cis_pdf_parser.py --pdf_file CIS_Red_Hat_Enterprise_Linux_7_Benchmark_v3.1.1.pdf --out_file rhel_7_controls.csv
```

## Output

The script will parse each page and extract the information corresponding to the following fields:

```
Rule, Profile Applicability, Description, Rationale, Audit, Remediation, CIS Controls
```

## Notes

**Tested against:**

* CIS_Oracle_Linux_7_Benchmark_v3.1.1
* CIS_Red_Hat_Enterprise_Linux_8_Benchmark_v1.0.1
* CIS_Red_Hat_Enterprise_Linux_7_Benchmark_v3.1.1

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

