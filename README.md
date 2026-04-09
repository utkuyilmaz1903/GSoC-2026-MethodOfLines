# 🚀 GSoC 2026: Comprehensive Non-Uniform Grid Support for MethodOfLines.jl

**Organization:** [NumFOCUS / SciML](https://sciml.ai/)  
**Applicant:** Utku Yılmaz  

Welcome to the central repository for my Google Summer of Code 2026 application. This repository contains my official proposal, curriculum vitae, and a structured overview of my active contributions and research within the SciML ecosystem.

## 📄 Application Documents
* [**GSoC 2026 Project Proposal**](./SciMLUtkuYilmazProposal.pdf) (PDF)
* [**Curriculum Vitae**](./Utku_Yilmaz_CV.pdf) (PDF)

## 🎯 Project Abstract
The goal of this project is to deliver comprehensive, end-to-end non-uniform grid support for `MethodOfLines.jl`. This includes refactoring basic schemes to handle variable step sizes, mathematically deriving and implementing native non-uniform stencils for advanced high-order schemes (like WENO), and establishing the core data structures necessary for future Finite Volume Method (FVM) integration.

## 🔬 Personal R&D & Feasibility Prototypes
To mitigate technical risks and prove architectural feasibility, I maintain a dedicated research repository and have developed several standalone prototypes:
* 📂 **[learning-sciML-pde](https://github.com/utkuyilmaz1903/learning-sciML-pde):** Contains custom 1D/2D FDM/FVM implementations, Fornberg benchmarks, and mathematical analysis of WENO smoothness indicators on clustered grids.

**Strategic Prototypes:**
* **Architectural POC ([Draft PR #535](https://github.com/SciML/MethodOfLines.jl/pull/535)):** Decoupled the differential discretizer to accept `AbstractVector` grid types.
* **WENO Engine Prototype ([Draft PR #538](https://github.com/SciML/MethodOfLines.jl/pull/538)):** Standalone 1D mathematical engine for non-uniform WENO weights featuring dynamic smoothness indicators.
* **Boundary Engine Prototype ([Draft PR #539](https://github.com/SciML/MethodOfLines.jl/pull/539)):** Zero-allocation, O(1) mathematical engine for 4-point one-sided finite difference weights integrating Kahan summation.
* **Dispatch Infrastructure Prototype ([Draft PR #542](https://github.com/SciML/MethodOfLines.jl/pull/542)):** Dispatch hub leveraging Julia’s Trait system to route between computational engines with zero runtime overhead.

## 🛠️ Contributions to the SciML Ecosystem

Below is a categorized overview of my core infrastructure fixes, bug resolutions, and non-uniform grid developments:

### ✅ Merged Core Architectural & Dispatch Fixes
* **SciMLBase.jl [[PR #1265]](https://github.com/SciML/SciMLBase.jl/pull/1265) / Resolves [Issue #1130](https://github.com/SciML/DifferentialEquations.jl/issues/1130):** Prevented silent CPU fallbacks in GPU simulations by fixing a dispatch trap in `EnsembleProblem`.
* **SciMLBase.jl [[PR #1258]](https://github.com/SciML/SciMLBase.jl/pull/1258):** Fixed a `MethodError` by dynamically typing analytic functions in `AutoSpecialize`.
* **MethodOfLines.jl [[Issue #445]](https://github.com/SciML/MethodOfLines.jl/issues/445):** Solved a critical mass leakage problem in age-of-infection SIR models by reformulating the system algebraically as a DAE.

### 🔄 Open/Active: Grid & Discretization Refactoring (MethodOfLines.jl)
* **[[PR #543]](https://github.com/SciML/MethodOfLines.jl/pull/543) & [[PR #541]](https://github.com/SciML/MethodOfLines.jl/pull/541):** Introduced a recursive well-posedness check in the discretization flow to gracefully catch missing boundary conditions, preventing complex `RuleRewriteError`s on non-uniform domains.
* **[[PR #70]](https://github.com/SciML/PDEBase.jl/pull/70) (Fixes [Issue #67](https://github.com/SciML/PDEBase.jl/issues/67)):** Addressed boundary resolution failures by implementing fallback `offset` dispatch methods for `LowerBoundary` and `UpperBoundary` types. Included rigorous safetestsets to prevent future regressions.
* **[[PR #533]](https://github.com/SciML/MethodOfLines.jl/pull/533):** Fixed a critical `BoundsError` in `UpwindScheme` by correcting hardcoded boundary coefficients logic for variable step sizes.
* **[[PR #532]](https://github.com/SciML/MethodOfLines.jl/pull/532):** Prevented infinite loops in `transform_pde_system!` by resolving boolean context errors.
* **[[PR #534]](https://github.com/SciML/MethodOfLines.jl/pull/534):** Added a foundational mathematical tutorial for non-uniform grid discretization to the official documentation.

### ⚙️ Merged: Core Symbolic Engine (SymbolicUtils.jl)
* **[[PR #884]](https://github.com/JuliaSymbolics/SymbolicUtils.jl/pull/884) (Fixes [Issue #876](https://github.com/JuliaSymbolics/SymbolicUtils.jl/issues/876)):** Fixed a scoping leak in nested `ArrayOp` substitution during scalarization. Implemented a zero-allocation, scope-aware substitution filter to unblock the evaluation of non-linear diffusion and advanced stencils (like WENO) on non-uniform domains.

## 📬 Contact Information
* **Email:** utkyilmz@gmail.com
* **GitHub:** [@utkuyilmaz1903](https://github.com/utkuyilmaz1903)
* **SciML Slack:** Utku Yılmaz *(Active for GSoC and technical discussions)* 
* **Julia Discourse:** [Utku_Yilmaz](https://discourse.julialang.org/u/utku_yilmaz/summary)
