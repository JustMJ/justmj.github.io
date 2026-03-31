# Multilevel Modeling (MLM) Tutorials for OB/I-O Psychology

**Course**: PSY 8XXX: Multilevel Modeling for Organizational Research  
**Target Audience**: Doctoral students in I-O/Organizational Psychology (UGA level)  
**Data Structure**: Employees nested within teams/organizations  
**Tools**: R (lme4, lmerTest, tidyverse, ggplot2, performance)

## Tutorial Overview

This suite of 5 comprehensive Quarto tutorials covers advanced topics in multilevel modeling with an emphasis on practical application to organizational research.

### Week 6: Cross-Level Interactions
**File**: `week06_cross_level_interactions.qmd`  
**Lines**: 427

Explores when and how group-level variables modify individual-level relationships.

**Key Topics**:
- Conceptual foundation: What is a cross-level interaction?
- Mathematical specification (γ₁₁ coefficient)
- Data generation with true interaction effects
- Model fitting in lme4 with random slopes
- Simple slopes analysis (±1 SD of moderator)
- Publication-ready interaction plots
- Effect sizes (Aguinis et al. 2013)
- Common pitfalls (centering, L2 sample size, interpretation)

**Practical Example**: Team climate moderates the effect of autonomy on job satisfaction

**Exercises**: 5+ hands-on "Try It Yourself" challenges

---

### Week 7: Model Comparison, Fit, and Estimation
**File**: `week07_model_comparison_fit.qmd`  
**Lines**: 470

Systematic approach to choosing among competing model specifications using likelihood ratio tests and information criteria.

**Key Topics**:
- ML vs. REML: Conceptual differences and when to use each
- Likelihood ratio tests for nested models
- AIC and BIC for non-nested comparison
- Nakagawa & Schielzeth pseudo-R² measures
- Marginal vs. conditional R²
- Step-by-step model building workflow
- Publication tables with formatted results
- Effect interpretation in presence of interactions

**Practical Example**: Building from null model → random intercept → random slope → L2 predictor → cross-level interaction

**Exercises**: Model selection, sensitivity analysis, competing hypotheses

---

### Week 8: Assumptions, Diagnostics, and Practical Issues
**File**: `week08_assumptions_diagnostics.qmd`  
**Lines**: 503

Comprehensive diagnostic toolkit for checking MLM assumptions and identifying data quality issues.

**Key Topics**:
- Assumption review (normality at L1 and L2, homoscedasticity, linearity, independence)
- Extracting and visualizing L1 residuals
- Level 2 random effects diagnostics
- Influence diagnostics (Cook's distance, leverage)
- Kenward-Roger vs. Satterthwaite degrees of freedom
- Heteroscedasticity detection and correction
- Missing data patterns (MAR vs. MCAR vs. MNAR)
- Robust standard errors (sandwich estimators)
- Complete diagnostic workflow

**Practical Example**: Full pipeline for assessing one complex model

**Exercises**: Outlier manipulation, random effects misspecification, heteroscedasticity exploration

---

### Week 9: Statistical Power for Multilevel Designs
**File**: `week09_power_analysis.qmd`  
**Lines**: 453

Design and power analysis specific to multilevel structures where L2 units matter more than L1 units.

**Key Topics**:
- Why L2 sample size dominates power calculations
- Effective sample size in presence of ICC
- Analytic power formulas (Maas & Hox 2005)
- Simulation-based power with simr package
- Power for main effects vs. cross-level interactions
- Power curves: exploring the design space
- Study planning workflow with realistic scenarios
- Rules of thumb and their limitations
- Sensitivity analysis

**Practical Example**: Designing organizational study with adequate power for detecting cross-level interaction

**Exercises**: Effect size variation, interaction vs. main effect power, unbalanced designs

---

### Week 10: Multilevel Mediation
**File**: `week10_multilevel_mediation.qmd`  
**Lines**: 492

Proper decomposition of mediation effects into within-group and between-group components.

**Key Topics**:
- Problem with naive mediation on nested data
- Types of multilevel mediation (1-1-1, 2-1-1, 2-2-1)
- Zhang, Zyphur, & Preacher (2009) framework
- Group-mean centering and effect decomposition
- Implementing within-team mediation (1-1-1)
- Implementing cross-level mediation (2-1-1)
- Bootstrapping indirect effects and confidence intervals
- Presenting results with path diagrams
- Complete worked example

**Practical Example**: Team climate → member psychological safety → job satisfaction (with within/between decomposition)

**Exercises**: Reverse mediation, competing mediators, moderated mediation

---

## Cross-Tutorial Features

### Data & Code Quality
- **Reproducible**: All data simulated with `set.seed(1234)`
- **Self-contained**: No external data files needed
- **Realistic**: Variables and effect sizes drawn from organizational psychology literature
- **Substantive**: Data-generating processes encode true theoretical relationships

### Pedagogy
- **Accessible language**: Written for doctoral psychologists, not statisticians
- **Mathematical intuition**: Equations explained conceptually, not just formally
- **Narrative interpretation**: Every code output followed by substantive meaning
- **Active learning**: Multiple "Try It Yourself" exercises per tutorial

### Organizational Context
All tutorials use consistent organizational scenario:
- **Outcome variables**: Job satisfaction, team performance
- **Individual predictors**: Autonomy, job complexity, tenure, psychological safety
- **Group predictors**: Team climate, leader support, team size
- **Structure**: ~500 employees nested in ~50 teams

### Technical Stack
- **Language**: R 4.0+
- **Core packages**: lme4, lmerTest
- **Visualization**: ggplot2
- **Data manipulation**: tidyverse (dplyr, tidyr)
- **Diagnostics**: performance
- **Document format**: Quarto (HTML output, code folding)

---

## How to Use

### For Instructors
1. Assign one tutorial per week (matches Week 6-10 titles)
2. Use as preparation material or assigned reading
3. Have students run code, modify parameters, complete exercises
4. Use exercises as basis for in-class discussion or assignments

### For Students
1. Read introduction and conceptual sections without code
2. Run code chunks in RStudio/Quarto and examine output
3. Modify data-generating parameters and re-run (e.g., change effect size, ICC)
4. Complete "Try It Yourself" exercises
5. Reference tutorials when building your own analyses

### For Thesis/Research
- Use simulated data examples as templates for your own research
- Adapt code for your organizational context
- Reference tutorials in methods sections
- Modify power analyses for your specific research questions

---

## Technical Notes

### Rendering
Each tutorial renders to self-contained HTML with interactive code folding:
```bash
quarto render week06_cross_level_interactions.qmd --to html
```

### Dependencies
Install required packages:
```r
pkgs <- c("lme4", "lmerTest", "tidyverse", "ggplot2", "performance")
install.packages(pkgs)
```

Optional packages for advanced work:
```r
install.packages(c("simr", "sandwich", "nlme"))
```

### Code Style
- Consistent naming conventions (e.g., `autonomy_c` for centered variables)
- Clear variable scoping
- Comments on non-obvious operations
- Reproducible random seeds

---

## Academic References

Key citations supporting tutorial content:

**Cross-Level Interactions**:
- Aguinis, H., Gottfredson, R. K., & Joo, H. (2013). Best-practice recommendations for defining, identifying, and handling outliers. *Organizational Research Methods*, 16(2), 270-301.
- Preacher, K. J., Curran, P. J., & Bauer, D. J. (2006). Computational tools for probing interactions in multiple linear regression, multilevel modeling, and latent curve analysis. *Journal of Educational and Behavioral Statistics*, 31(4), 437-448.

**Model Comparison & Fit**:
- Nakagawa, S., & Schielzeth, H. (2013). A general and simple method for obtaining R² from generalized linear mixed-effects models. *Methods in Ecology and Evolution*, 4(2), 133-142.

**Power Analysis**:
- Maas, C. J., & Hox, J. J. (2005). Sufficient sample sizes for multilevel modeling. *Methodology: European Journal of Research Methods for the Behavioral and Social Sciences*, 1(3), 86-92.

**Multilevel Mediation**:
- Zhang, Z., Zyphur, M. J., & Preacher, K. J. (2009). Testing multilevel mediation using hierarchical linear models: Problems and solutions. *Organizational Research Methods*, 12(4), 695-719.

---

## Directory Structure

```
MLM_Tutorials/
├── INDEX.md                           (This file)
├── CREATION_SUMMARY.txt               (Summary of all tutorials)
├── week06_cross_level_interactions.qmd
├── week07_model_comparison_fit.qmd
├── week08_assumptions_diagnostics.qmd
├── week09_power_analysis.qmd
└── week10_multilevel_mediation.qmd
```

---

## Version & Date

**Created**: 2026-03-29  
**Format**: Quarto (.qmd)  
**Total Content**: 2,345 lines across 5 files  
**Target Audience**: Doctoral I-O/Organizational Psychology  

---

*These tutorials are designed to be living documents. Instructors are welcome to adapt code examples, update references, and modify exercises for their specific courses.*
