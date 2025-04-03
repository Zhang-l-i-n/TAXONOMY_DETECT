# LITE: LLM-Impelled Efficient Taxonomy Evaluation

[![arXiv](https://img.shields.io/badge/arXiv-2504.00695-b31b1b.svg)](https://arxiv.org/abs/2504.01369)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE) 

## Abstract
This repository implements LITE (**L**LM-**I**mpelled efficient **T**axonomy **E**valuation), a novel framework for systematic taxonomy evaluation leveraging Large Language Models (LLMs). LITE addresses critical challenges in taxonomy assessment through:
- **Hierarchical decomposition** of taxonomies into manageable substructures
- **Cross-validated scoring** with standardized input formats
- **Multi-dimensional metrics** (SCA, HRR, HRE, HRI) aligned with domain requirements
- **Penalty mechanisms** for handling structural anomalies

Our comprehensive experiments demonstrate LITE's superior performance in detecting semantic inconsistencies (89.7% accuracy), logical contradictions (93.2% recall), and structural flaws (F1=0.91) compared to conventional methods.

## Key Features
- 🧠 **LLM-powered analysis**: GPT-4 integration for semantic reasoning
- 📊 **Multi-level evaluation**: Concept/relation/hierarchy assessment
- ⚙️ **Dynamic adaptation**: Automatic span adjustment for subtree selection
- 📈 **Quantitative metrics**: 4-dimension scoring system with interpretability
- 🛡️ **Anomaly detection**: Structural consistency validation

## Installation
```bash
git clone https://github.com/Zhang-l-i-n/TAXONOMY_DETECT.git
cd TAXONOMY_DETECT
pip install -r requirements.txt
```

## Quick Start
### 1. Prepare Taxonomy Data
Organize your taxonomy as JSONL:
```json
["artificial intelligence", "ghosting"]
["artificial intelligence", "machine learning"]
```
Save to `data/taxonomy/<your_taxonomy>/`


### 2. Run Evaluation
```bash
python main/score.py --input_file ./data/taxonomy.jsonl --output_dir results
```

## Advanced Configuration
### Evaluation Modes
| Mode | Description | Use Case |
|------|-------------|----------|
| `dynamic` | Adaptive subtree sizing (Eq.1-3) | Large-scale taxonomies |
| `static` | Fixed-span evaluation | Benchmark comparisons |

### Metrics Definition
1. **SCA** (Single Concept Accuracy): Term clarity score [0-10]
2. **HRR** (Hierarchy Relationship Rationality): Logical consistency [0-10] 
3. **HRE** (Hierarchy Relationship Exclusivity): Semantic distinctiveness [0-10]
4. **HRI** (Hierarchy Relationship Independence): Structural redundancy [0-10]

## Experimental Results
### Performance Comparison (F1 Scores)
| Dataset | SCA | HRR | HRE | HRI |
|---------|-----|-----|-----|-----|
| MAG-CS | 0.89 | 0.92 | 0.85 | 0.88 | 
| Ali-Taxo | 0.91 | 0.84 | 0.88 | 0.83 |


## Citation
If you use LITE in your research, please cite:
```bibtex
@misc{zhang2025litellmimpelledefficienttaxonomy,
      title={LITE: LLM-Impelled efficient Taxonomy Evaluation}, 
      author={Lin Zhang and Zhouhong Gu and Suhang Zheng and Tao Wang and Tianyu Li and Hongwei Feng and Yanghua Xiao},
      year={2025},
      eprint={2504.01369},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2504.01369}, 
}
```
