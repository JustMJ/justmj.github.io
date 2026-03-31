# Multilevel Modeling Tutorials for Doctoral I-O Psychology Seminar

## Overview

Five comprehensive Quarto (.qmd) tutorials on multilevel modeling (MLM) for organizational behavior research. Each tutorial is 400-600 lines with embedded R code, narrative explanations, visualizations, and hands-on exercises.

All tutorials use a consistent simulated organizational dataset (500 employees in 50 teams) with realistic variables and data-generating processes. All code uses `set.seed(1234)` for reproducibility.

## Files

### Week 1: Introduction to Nesting (week01_introduction_nesting.qmd)
**Topic**: Why Multilevel Modeling? The Logic of Nesting in Organizations

- Introduces the concept of nested data structures in organizations
- Creates a realistic simulated employee-team dataset
- Demonstrates the problem with OLS when data are nested
- Conducts a Type I error simulation showing inflated error rates (~20-30% vs. nominal 5%)
- Explains ecological fallacy and atomistic fallacy with code examples
- Visualizes nested data with spaghetti plots and team boxplots
- Previews what MLM tools offer

**Lines**: 424 | **Code chunks**: 8 | **Key concepts**: Nesting, non-independence, Type I error inflation

---

### Week 2: Unconditional Model and ICC (week02_unconditional_model_icc.qmd)
**Topic**: Partitioning Variance—The Unconditional Model and ICC

- Develops the unconditional (null) model equation with intuitive notation
- Fits the null model using `lmer(outcome ~ 1 + (1 | team))`
- Extracts and interprets variance components (tau-squared and sigma-squared)
- Computes the Intraclass Correlation Coefficient (ICC) three ways
- Explains ICC substantively: proportion of variance at each level
- Introduces design effects and effective sample size reduction
- Creates caterpillar plots visualizing random intercepts with CIs
- Compares ICCs across multiple outcomes

**Lines**: 417 | **Code chunks**: 8 | **Key concepts**: ICC, variance decomposition, random intercepts, design effects

---

### Week 3: Random Intercept Models (week03_random_intercept_models.qmd)
**Topic**: Random Intercept Models—Adding Predictors Across Levels

- Develops random intercept model equations at both Level 1 and 2
- Fits models progressively: Level-1 only → Level-2 only → Combined
- Compares OLS estimates to MLM estimates (proper standard errors)
- Calculates pseudo-R² at both levels, showing variance explained
- Uses likelihood ratio tests to compare nested models
- Visualizes team-specific fitted lines with ggplot2
- Walks through a complete substantive example
- Includes advanced diagnostic discussion of assumptions

**Lines**: 463 | **Code chunks**: 10 | **Key concepts**: Fixed vs. random effects, cross-level effects, variance explained

---

### Week 4: Random Slopes Models (week04_random_slopes.qmd)
**Topic**: Random Slopes and Model Building Strategy

- Explains why slopes might vary across groups
- Develops random slope model equations with slope-intercept correlation
- Fits models with `(1 + predictor | group)` syntax
- Extracts and interprets slope heterogeneity
- Visualizes team-specific regression lines (non-parallel)
- Conducts likelihood ratio tests comparing random intercept vs. random slope
- Explores intercept-slope correlation substantively
- Discusses model-building strategies: "keep it maximal" vs. bottom-up vs. theory-driven
- Addresses convergence issues and practical solutions

**Lines**: 478 | **Code chunks**: 9 | **Key concepts**: Slope heterogeneity, convergence, model building

---

### Week 5: Centering Decisions (week05_centering_decisions.qmd)
**Topic**: Centering Decisions—Not Just a Technical Choice

- Frames centering as a substantive decision, not just technical preprocessing
- Distinguishes within-team and between-team research questions
- Explains Grand-Mean Centering (CGM): when and why to use it
- Explains Group-Mean Centering (CWC): isolating within-team effects
- Demonstrates Simpson's Paradox: opposite effects at different levels
- Introduces Raudenbush formulation: including both within and between in one model
- Connects centering to organizational behavior theory
- Creates decision framework for choosing centering approach
- Highlights common mistakes (collinearity, over-interpretation, etc.)

**Lines**: 563 | **Code chunks**: 11 | **Key concepts**: Within vs. between effects, contextual effects, Simpson's paradox

---

## Key Features Across All Tutorials

### Data and Reproducibility
- Consistent simulated dataset across all tutorials
- 500 employees nested in 50 teams (~10 per team)
- Variables: job_satisfaction, autonomy, performance, tenure, team_climate, team_size
- `set.seed(1234)` at start of each tutorial ensures reproducibility
- Realistic data-generating process with genuine between-team variance

### Code Quality
- All R code uses `tidyverse` for data manipulation and visualization
- `ggplot2` for publication-quality plots
- `lme4` and `lmerTest` for multilevel models
- `performance` package for ICC and effect size computation
- Every code chunk has explanatory narrative following it

### Pedagogical Structure
- **Introduction**: Motivates the topic with real organizational examples
- **Conceptual development**: Equations with intuitive explanations (not overly formal)
- **Hands-on code**: Step-by-step walkthroughs of model fitting and interpretation
- **Visualization**: Spaghetti plots, boxplots, caterpillar plots, regression lines
- **Application**: Complete worked examples showing real research flow
- **Exercises**: 5 "Try It Yourself" exercises per tutorial, ranging from replication to extension

### Target Audience
- Doctoral students with PhD in I-O psychology
- Some statistics background (understanding of OLS, hypothesis testing)
- Academic but accessible tone: explain intuitions without assuming deep technical knowledge
- Organizational behavior focus: examples drawn from team dynamics, leadership, engagement

---

## How to Use These Tutorials

1. **Render to HTML**: Use Quarto (`quarto render week01_*.qmd`) to produce HTML with interactive code folding
2. **Work through sequentially**: Week 1→5 builds progressively; Week N assumes Week N-1 concepts
3. **Run code interactively**: Copy code chunks into R console or RStudio to experiment
4. **Do the exercises**: Try It Yourself sections are essential for learning
5. **Adapt data**: Replace simulated data with your own for deeper practice

---

## Technical Requirements

- **R packages**: tidyverse, lme4, lmerTest, performance, broom.mixed, gridExtra
- **Quarto**: For rendering .qmd to HTML (optional; files can be read as markdown)
- **R version**: 4.0+ recommended

---

## Notes for Instructors

- YAML headers use `code-fold: true` so students can hide/show code as needed
- All code is reproducible with no external data files
- Exercises have multiple difficulty levels (replication → extension → theory)
- Encourage students to modify code (e.g., different sample sizes, predictors) to deepen understanding
- These tutorials assume ~2 hours per week; adjust pace as needed

---

## Summary Statistics

| Metric | Total |
|--------|-------|
| Total lines of code | 2,345 |
| Code chunks | 46 |
| Exercises (5 per tutorial) | 25 |
| Visualizations | 20+ |
| Substantive examples | 15+ |

---

**Created**: March 2026  
**Author**: Instructor Name  
**Course**: PSY 8XXX Multilevel Modeling for Organizational Research
