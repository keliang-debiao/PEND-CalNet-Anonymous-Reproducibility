PEND-CalNet Anonymous Reproducibility Package
Overview
This repository contains the source code, configuration files, workflow scripts, tests, documentation, reference records, and environment specifications for PEND-CalNet, a framework for cross-corpus calibrated Tibetan dialect identification.
Repository Contents
Path	Contents
src/pend_calnet/	Python implementation of data processing, acoustic feature extraction, model components, training objectives, calibration, evaluation, statistical analysis, robustness analysis, baselines, and reporting utilities
configs/	Main experiment configuration, baseline settings, dataset definitions, and component-variant configurations
scripts/	Command-line scripts for data auditing, manifest generation, fold construction, training, hyperparameter search, baseline evaluation, ablation analysis, external evaluation, robustness analysis, statistical testing, profiling, verification, and report-asset generation
tests/	Unit tests for configuration loading, model tensor shapes, loss functions, metrics, and statistical utilities
manifests/	Manifest schema and documentation for constructing corpus indexes and split files
results/reference_records/	Reference record files used by the package verification and reporting workflow
logs/	Reference run logs and log-file documentation
artifacts/	Destination directory for locally generated checkpoints, predictions, tables, figures, and analysis files


Source Modules
The src/pend_calnet/ package includes:
- audio.py — waveform handling and acoustic-feature extraction;
- data.py — manifest loading, dataset construction, preprocessing, and batching;
- model.py — PEND-CalNet model components and forward computation;
- losses.py — classification, phonological, disentanglement, contrastive, and consistency objectives;
- calibration.py — calibration components and probability adjustment utilities;
- training.py — training, validation, checkpointing, and model-selection procedures;
- metrics.py — classification and calibration metric utilities;
- statistics.py — paired comparison and statistical-analysis utilities;
- robustness.py — robustness evaluation utilities;
- baselines.py — traditional baseline implementations;
- neural_baselines.py — neural and foundation-model baseline implementations;
- workflow.py — shared workflow orchestration functions;
- reporting.py — table, figure, and report-asset generation utilities;
- config.py — configuration parsing and validation;
- verify.py — package-integrity verification entry point.
Configuration Files
The configs/ directory contains:
- pend_calnet.yaml for the main model, optimization, calibration, and evaluation settings;
- baselines.yaml for comparator definitions;
- datasets/tibmd.yaml for the TIBMD@MUC development corpus;
- datasets/slr149.yaml for the Tibetan Greetings external corpus;
- datasets/finance.yaml for the TibSpeech-3D Finance external corpus;
- variants/ for the full configuration, mean-pooling variant, and component-removal variants.
Workflow Scripts
The scripts/ directory contains:
- build_manifest.py and audit_data.py for corpus indexing and data checks;
- build_folds.py for speaker-grouped fold construction;
- train_cv.py and fit_final.py for cross-validation and final-model fitting;
- search_hyperparameters.py and aggregate_search.py for configuration search and aggregation;
- run_baselines.py and run_ablations.py for comparator and component analyses;
- evaluate_external.py for frozen external evaluation;
- run_robustness.py for robustness analyses;
- run_statistics.py and run_analyses.py for statistical and auxiliary analyses;
- profile_model.py for model-efficiency profiling;
- build_method_figures.py and build_report_assets.py for generating manuscript assets;
- verify_package.py for configuration, file-structure, arithmetic, and anonymity checks;
- run_full_pipeline.sh for coordinating the complete workflow.
Documentation
The package includes the following documentation files:
- DATA_ACCESS.md — public dataset sources, licenses, and data-placement boundaries;
- REPRODUCIBILITY.md — reproducibility workflow and execution guidance;
- MODEL_SPECIFICATION.md — tensor interfaces, model components, training-only branches, and checkpoint contents;
- BASELINE_PROTOCOL.md — common data partitions, calibration rules, and comparison procedures for baseline models;
- RESULTS_PROVENANCE.md — distinction between packaged reference records and locally generated files;
- ANONYMITY.md — anonymous-review release checklist;
- manifests/README.md — manifest format and construction notes;
- logs/README.md — log-file organization and interpretation notes.
Environment and Packaging Files
The repository also contains:
- environment.yml and requirements.txt for the recorded software environment;
- pyproject.toml for Python package metadata and installation;
- Makefile for common workflow commands;
- CITATION.cff for software citation metadata;
- LICENSE for the MIT License;
- .gitignore for excluding local data and generated artifacts.
Data Boundary
The repository does not include speech recordings, transcripts, or redistributed provider metadata. Dataset locations and access information are described in DATA_ACCESS.md, while generated manifests and outputs are stored locally in the designated directories.
