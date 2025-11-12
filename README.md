# Cloud ETL Pipeline Diagrams

[![Python](https://img.shields.io/badge/Python-3.7+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![AWS](https://img.shields.io/badge/AWS-Cloud-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/)
[![Diagrams](https://img.shields.io/badge/Diagrams-as_Code-00ADD8?style=for-the-badge&logo=graphviz&logoColor=white)](https://diagrams.mingrammer.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

Python-based architecture diagrams for AWS ETL pipeline infrastructure using diagrams-as-code.

## Overview

This repository contains programmatically generated architecture diagrams that visualize a multi-source retail data ETL pipeline on AWS. By treating diagrams as code, we ensure they stay version-controlled, reproducible, and easy to maintain alongside infrastructure changes.

## Architecture

The pipeline ingests data from multiple sources (Google Merchandise Store, Amazon Product Reviews, and Bluesky Firehose API) and processes it through several stages:

- **Data Sources**: S3 inventory tables, NoSQL product data, and API streaming data
- **Ingestion Tools**: Amazon DMS, AWS Glue, Kinesis Firehose, and S3 bulk uploads
- **Data Transformation**: AWS Glue ETL jobs processing CSV, JSON, and raw media files
- **Data Zones**: Landing Zone → Clean Zone → Curated Zone
- **Data Catalog**: AWS Glue Data Catalog for metadata management
- **Data Access & Consumers**: Query and analytics layers (placeholder for future implementation)

## Prerequisites

- Python 3.7+
- pip or conda package manager
- Graphviz (required by the `diagrams` library)

### Install Graphviz

**macOS:**
```bash
brew install graphviz
```

**Ubuntu/Debian:**
```bash
sudo apt-get install graphviz
```

**Windows:**
Download from [graphviz.org](https://graphviz.org/download/) or use:
```bash
choco install graphviz
```

## Installation

1. Clone the repository:
```bash
git clone https://github.com/sparkcrafted/cloud-etl-pipeline-diagrams.git
cd cloud-etl-pipeline-diagrams
```

2. Install Python dependencies:
```bash
pip install -r requirements.txt
```

Or if using conda:
```bash
conda install diagrams
```

## Usage

Run the diagram generation script:

```bash
python generate_diagram.py
```

This will create a PNG file (e.g., `aws_etl_pipeline.png`) in the output directory showing the complete architecture.

### Customization

You can modify the diagram by editing `generate_diagram.py`:
- Add/remove AWS services
- Change data flow connections
- Adjust layout and grouping
- Modify colors and styling
- Add annotations or labels

## Project Structure

```
cloud-etl-pipeline-diagrams/
├── README.md
├── requirements.txt
├── generate_diagram.py      # Main diagram generation script
├── output/                   # Generated diagram files
│   └── aws_etl_pipeline.png
└── docs/                     # Additional documentation
```

## Benefits of Diagrams as Code

- **Version Control**: Track changes to architecture over time
- **Automation**: Regenerate diagrams automatically in CI/CD pipelines
- **Consistency**: Maintain uniform styling across all diagrams
- **Documentation**: Keep architecture docs synchronized with infrastructure
- **Collaboration**: Review diagram changes through pull requests

## Related Repositories

- [AWS ETL Pipeline IaC](#) - Infrastructure as Code for deploying this pipeline (link to your IaC repo)

## Technologies Used

- [Diagrams](https://diagrams.mingrammer.com/) - Python library for creating cloud architecture diagrams
- AWS Services: S3, DMS, Glue, Kinesis Firehose, Glue Data Catalog
- Graphviz - Graph visualization software

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/new-diagram`)
3. Commit your changes (`git commit -m 'Add new architecture diagram'`)
4. Push to the branch (`git push origin feature/new-diagram`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**Warren** - [GitHub Profile](https://github.com/sparkcrafted)

## Acknowledgments

- Built with [Diagrams](https://diagrams.mingrammer.com/) by MinJae Kwon
- Architecture based on AWS best practices for data lake design
- Part of coursework at Morgan State University's Earl G. Graves School of Business and Management

---

*Generated diagrams represent the logical architecture of the ETL pipeline and may be updated as the infrastructure evolves.*
