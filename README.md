<div align="center">

# Hey, I'm JeknJok

**Software Engineering · Systems · Machine Learning · Computer Vision · Data Engineering · Game Development**

I build software across the stack — from production APIs and data-processing libraries to machine-learning pipelines, low-level systems, and large-scale game architecture.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

</div>

---
- Experience developing and maintaining **production REST APIs**
- Currently contributing to a **multi-backend Python data-quality and profiling library**
- Interested in **systems programming, software architecture, data engineering, ML/CV, compilers, and performance**
- Creator of game projects with **90K+ combined downloads**
- Built deep-learning pipelines using datasets with **46K+ images**
- I like understanding what abstractions are doing underneath rather than treating frameworks as black boxes

---

## Featured Projects

### Data Quality & Dataframe Profiling Library

<a href="https://github.com/rwadisaputro/data_quality">
  <img src="https://github-readme-stats.vercel.app/api/pin/?username=rwadisaputro&repo=data_quality&hide_border=true" />
</a>

**Python · pandas · Polars · PySpark · NumPy · HyperLogLog · Distributed Data Processing**

Currently contributing to a backend-neutral Python library for **dataframe intake, schema discovery, structural profiling, and scalable data-quality analysis** across pandas, Polars, and Apache Spark.

The project is designed around an important constraint: profiling should respect the dataframe's **native execution engine** instead of blindly converting everything into pandas.

Current functionality includes:

- Automatic identification of **pandas, Polars, and PySpark** dataframe backends
- Native physical-schema discovery while preserving backend-specific data types
- Metadata-aware row and column counting
- Support for eager, lazy, local, distributed, and streaming dataframe execution models
- Structured, JSON-compatible profiling output and lineage
- Backend-neutral APIs with backend-specific execution adapters

A major area I've worked on is **cardinality estimation** — determining how many distinct values exist in a column without requiring an arbitrarily large exact set.

The cardinality pipeline uses an adaptive strategy:

```text
column values
      ↓
exact unique tracking
      ↓
memory / cardinality threshold exceeded?
      │
   no │          yes
      ↓            ↓
exact result    HyperLogLog
                    ↓
             approximate result
```

This allows small and moderate columns to remain **exact**, while high-cardinality data can automatically transition to a bounded-memory probabilistic representation.

Work in this area involves:

- **HyperLogLog** approximate distinct counting
- 64-bit hashing and register-based cardinality estimation
- Linear Counting correction for lower-cardinality ranges
- Configurable precision and memory/error tradeoffs
- One-way promotion from exact state to approximate HLL state
- Vectorized NumPy processing
- Backend-specific hashing and batching strategies
- Null, NaN, dtype, and equality-semantics handling
- Sketch compatibility and safe merge semantics

The backend implementations have different execution strategies.

**pandas**
- Dtype-specialized NumPy processing paths
- Vectorized hashing
- Exact-state tracking before HLL promotion
- Specialized handling for integers, floats, strings, categoricals, datetimes, periods, intervals, and object columns

**Polars**
- Native schema inspection
- Bounded processing of eager and lazy frames
- Vectorized native hashing
- Streaming-oriented processing without unnecessary dataframe conversion

**PySpark**
- Distributed exact distinct discovery
- Automatic fallback to distributed HLL computation for large cardinalities
- Spark SQL execution for register computation
- Collection of only compact HLL register state rather than full source data

The project places heavy emphasis on **correctness, explicit execution behavior, bounded memory use, reproducible hashing semantics, and testability**. The cardinality implementation maintains comprehensive statement and branch test coverage.

---

### Semantic Skin Segmentation

<a href="https://github.com/JeknJok/Semantic-Skin-Segmentation">
  <img src="https://github-readme-stats.vercel.app/api/pin/?username=JeknJok&repo=Semantic-Skin-Segmentation&hide_border=true" />
</a>

**PyTorch · DeepLabV3 · ResNet50 · OpenCV · Albumentations · NumPy**

Pixel-level human skin segmentation using a DeepLabV3-ResNet50 architecture.

- Trained and evaluated on **46,000+ images**
- Custom preprocessing and augmentation pipeline
- BCE + Dice based segmentation objectives
- AdamW optimization and learning-rate scheduling
- IoU-focused evaluation
- Best validation **mIoU: 0.7059**

---

### Game Project

**Game Systems · Java · mcfunction · JSON · Data-Driven Architecture**

A long-running RPG/game-engineering project built within Minecraft's constrained execution environment.

Built systems including:

- Boss AI and state machines
- Custom combat and damage systems
- Multiplayer-safe state management
- RPG progression and item systems
- Event and quest architecture
- Large-scale command scheduling
- Performance optimization
- Procedural and scripted encounters
- Custom audiovisual systems and assets

Projects I've worked on in this space have accumulated **90K+ combined downloads**.

> Source repositories are currently private. A public technical showcase is planned.

---

### Transportation Mode Prediction

**Python · pandas · scikit-learn · GPS · Accelerometer Data**

Machine-learning pipeline for identifying transportation modes using only GPS and accelerometer sensor data.

Worked on:

- Sensor-data preprocessing
- Time-series feature engineering
- Exploratory data analysis
- Classification
- Cross-validation
- Class imbalance
- Confusion-matrix and error analysis

---

### Systems Programming

**C · C++ · Linux · Networking · Concurrency · Memory Management**

Projects exploring how software behaves below the application layer, including implementations of:

`Unix Shell` · `Memory Allocator` · `Multithreaded MapReduce` · `Networked Chat` · `SHA-256 Blockchain`

Topics I've worked with include:

- Processes and threads
- Synchronization and concurrency
- Virtual memory
- Memory allocation
- Filesystems
- System calls
- Socket programming
- Build systems
- Sanitizers and debugging
- Proof-of-work and cryptographic hashing

---

## Technical Stack

<table>
<tr>
<td valign="top" width="33%">

### Languages

- Python
- C
- C++
- Java
- C#
- JavaScript
- TypeScript
- PHP
- SQL
- MATLAB

</td>
<td valign="top" width="33%">

### ML / Data

- PyTorch
- Torchvision
- OpenCV
- NumPy
- pandas
- Polars
- PySpark
- Spark SQL
- scikit-learn
- Albumentations
- matplotlib

</td>
<td valign="top" width="33%">

### Software / Systems

- Linux
- Git / GitHub
- Spring Boot
- REST / HTTP
- Node.js
- React
- MySQL
- CMake
- Make

</td>
</tr>
</table>

---

## What I'm Interested In

```text
systems programming        software architecture
operating systems          data engineering
data quality               distributed systems
machine learning           computer vision
performance optimization   concurrency
memory management          probabilistic algorithms
compilers                  programming languages
game architecture          algorithms & data structures
```
