# 🚀 GSoC 2026: Comprehensive Non-Uniform Grid Support for MethodOfLines.jl

**Organization:** [NumFOCUS / SciML](https://sciml.ai/)  
**Applicant:** Utku Yılmaz  

Welcome to the central repository for my Google Summer of Code 2026 application. This repository contains my official proposal, curriculum vitae, and a structured overview of my active contributions and research within the SciML ecosystem.

## 📄 Application Documents
* [**GSoC 2026 Project Proposal**](./SciMLUtkuYilmazProposal.pdf) (PDF)
* [**Curriculum Vitae**](./Utku_Yilmaz_CV.pdf) (PDF)

## 🔬 Personal R&D & Prototypes
Before modifying the core SciML codebase, I extensively researched and prototyped the necessary mathematics (Fornberg algorithm, WENO smoothness indicators for variable spacing) and identified the exact architectural bottlenecks. 
* 📂 **[learning-sciML-pde](https://github.com/utkuyilmaz1903/learning-sciML-pde):** My dedicated research repository containing custom non-uniform FDM/FVM implementations, performance benchmarks, and proof-of-concepts.

## 🛠️ Active & Merged Contributions to SciML
Below is a list of my active pull requests targeting core infrastructure, bug fixes, and non-uniform grid support:

### ✅ Merged & Resolved (Closed by Maintainers)
* **SciMLBase.jl [[#1258]](https://github.com/SciML/SciMLBase.jl/pull/1258):** Fix hardcoded type in `AutoSpecialize`
* **MethodOfLines.jl [[Issue #445]](https://github.com/SciML/MethodOfLines.jl/issues/445):** Resolved mass leakage in age-structured SIR PDEs. Diagnosed boundary PDE-ODE coupling failures and formulated a DAE-based hard constraint solution, officially acknowledged and closed by Chris Rackauckas.

### 🚧 Proof of Concept (Draft)
* **MethodOfLines.jl [[#535]](https://github.com/SciML/MethodOfLines.jl/pull/535):** Proof of Concept: Non-Uniform Grid Ingestion *(Direct foundation for this project)*

### 🔄 Open PRs & Discussions
* **MethodOfLines.jl [[#533]](https://github.com/SciML/MethodOfLines.jl/pull/533):** Fix `BoundsError` in `UpwindScheme`
* **MethodOfLines.jl [[#532]](https://github.com/SciML/MethodOfLines.jl/pull/532):** Fix infinite loop in `transform_pde_system!`
* **MethodOfLines.jl [[#534]](https://github.com/SciML/MethodOfLines.jl/pull/534):** Add non-uniform grid tutorials to docs

## 📬 Contact Information
* **Email:** utkyilmz@gmail.com
* **GitHub:** [@utkuyilmaz1903](https://github.com/utkuyilmaz1903)
* **SciML Slack:** Utku Yılmaz *(Active for GSoC and technical discussions)* (https://julialang.slack.com/team/U0AGVEXKJ07)
* **Julia Discourse:** [Utku_Yilmaz](https://discourse.julialang.org/u/utku_yilmaz/summary)
