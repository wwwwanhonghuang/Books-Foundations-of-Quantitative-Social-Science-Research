[] Add the discussion of research scheme, (国际政治学概论 5ed. p19)

Excellent


! Research design is crucial. Let's break down what needs to be covered:

**Phase 1: From Concepts to Operationalization**

**1. Conceptualization**
- Define theoretical constructs clearly
- Distinguish conceptual vs operational definitions
- Identify dimensions of complex constructs
- Classical: Literature-based concept definition
- Modern: Data-driven concept discovery (e.g., topic modeling, embedding spaces)

**2. Operationalization**
- Translate abstract concepts into measurable variables
- Validity considerations (construct, content, criterion)
- Reliability considerations (consistency, stability)
- Classical: Psychometric scales, validated instruments
- Modern: Behavioral traces, digital phenotyping, multimodal data

**Phase 2: General Research Design Methods**

**A. Experimental Designs (Classical)**
- Randomized Controlled Trials (RCT)
- Between-subjects vs within-subjects
- Factorial designs
- Pre-test/post-test designs
- Control groups and manipulation checks

**B. Quasi-Experimental Designs**
- Difference-in-differences (DiD)
- Regression discontinuity design (RDD)
- Interrupted time series
- Propensity score matching
- Instrumental variables

**C. Observational Designs (Classical)**
- Cross-sectional studies
- Longitudinal/panel studies
- Case-control studies
- Cohort studies
- Survey designs

**D. Modern/Computational Designs**
- A/B testing at scale (online experiments)
- Natural experiments with big data
- Synthetic control methods
- Regression discontinuity with machine learning
- Causal inference with observational big data

**Phase 3: Core Considerations Across All Designs**

**1. Causal inference framework**
- Potential outcomes framework (Rubin causal model)
- Directed Acyclic Graphs (DAGs)
- Confounding, mediation, moderation
- Classical: Experimental control
- Modern: Causal discovery algorithms, do-calculus

**2. Sampling and generalizability**
- Probability vs non-probability sampling
- Power analysis and sample size
- External validity
- Classical: Representative sampling
- Modern: Convenience samples with weighting, online panels

**3. Measurement strategy**
- Direct vs indirect measurement
- Self-report vs behavioral observation
- Single vs multiple indicators
- Classical: Questionnaires, structured observation
- Modern: Passive sensing, digital traces, neuroimaging

**4. Control strategies**
- Randomization
- Matching
- Statistical control
- Design-based vs model-based control

**5. Validity threats**
- Internal validity (can we make causal claims?)
- External validity (can we generalize?)
- Construct validity (are we measuring what we think?)
- Statistical conclusion validity (appropriate analysis?)

**Module structure suggestion:**

```
03-research-design/
├── 01-conceptualization.tex           # Concepts to variables
├── 02-operationalization.tex          # Measurement strategy
├── 03-experimental-designs.tex        # RCT, factorial, etc.
├── 04-quasi-experimental.tex          # DiD, RDD, IV, etc.
├── 05-observational-designs.tex       # Surveys, longitudinal, etc.
├── 06-causal-inference.tex            # DAGs, potential outcomes
├── 07-sampling-power.tex              # Who to study, how many
├── 08-validity-threats.tex            # What can go wrong
├── 09-modern-designs.tex              # Computational methods
└── 10-integration.tex                 # Choosing the right design
```

**For clinical psychology context specifically:**

Add emphasis on:
- Clinical vs subclinical populations
- Diagnostic operationalization (DSM, ICD criteria)
- Symptom measurement (validated scales)
- Ethical considerations (vulnerable populations)
- Treatment vs prevention designs
- Clinical trials methodology

**What else should be included? Or should we reorganize this structure?**


## claud one

Excellent systematic thinking! You're developing a **formal framework for operationalization**. Let me structure this:

**Formal Framework for Operationalization**

**Step 1: Entity Recognition and Typing**

Identify all entities and classify them:
- **E₁**: Population entities (adolescents, patients, students)
- **E₂**: Intervention entities (CBT, medication, training)
- **E₃**: Outcome entities (depression, performance, behavior)
- **E₄**: Contextual entities (time, setting, dosage)

**Step 2: Entity Quantification (E → ℝⁿ)**

**A. Population entities (E₁)**
- **Categorical attributes**: Demographics
  - Age: discrete (13, 14, ..., 17) or continuous
  - Gender: {male, female, other}
  - Clinical status: {diagnosed MDD, subthreshold, control}
- **Continuous attributes**: Individual differences
  - Baseline symptom severity: BDI-II ∈ [0, 63]
  - Cognitive function: z-scores
  - Socioeconomic status: composite index

**B. Intervention entities (E₂)**
- **Structural parameters**:
  - Duration: number of sessions (discrete: {8, 12, 16})
  - Intensity: sessions per week (continuous or discrete)
  - Fidelity: adherence score ∈ [0, 1]
- **Content parameters**:
  - Component presence: binary vector (cognitive restructuring: {0,1}, behavioral activation: {0,1})
  - Dosage: homework completion rate ∈ [0, 1]
- **Classical**: Discrete treatment conditions {CBT, Control}
- **Modern**: Treatment as continuous/multidimensional (dose-response, component analysis)

**C. Outcome entities (E₃)**
- **Direct measures**: 
  - Symptom scales: BDI-II ∈ [0, 63]
  - Categorical: Remission {0, 1}
- **Latent constructs**: Factor analysis, IRT
  - Depression as latent variable θ
  - Observed items x₁, x₂, ..., xₖ ~ f(θ)
- **Temporal structure**: Repeated measures
  - y(t) for t ∈ {baseline, week4, week8, week12}

**Step 3: Action/Process Quantification**

**Treatment as a process:**
- **Discrete-time process**: Treatment stage s ∈ {1, 2, ..., T}
- **Continuous-time process**: Treatment exposure τ(t)
- **Event-based**: Treatment components applied {c₁, c₂, ..., cₖ}

**Formalization approaches:**

**A. Set-theoretic**:
- Treatment T ⊆ C (subset of possible components)
- CBT = {cognitive_restructuring, behavioral_activation, homework}
- Control = ∅

**B. Vector representation**:
- Treatment as vector: **t** = [duration, intensity, fidelity, component₁, ..., componentₖ]
- CBT = [12, 1.0, 0.85, 1, 1, 0, ...]

**C. Functional representation**:
- Treatment as function: T: Time → Intervention_state
- T(t) describes what happens at each timepoint

**Step 4: Relation Quantification**

**A. Entity-Entity relations (Population characteristics)**
- **Correlation structure**: R(E₁, E₁)
  - Age × Baseline_severity: correlation matrix
  - Comorbidity patterns: network structure

**B. Entity-Treatment relations (Treatment assignment/selection)**
- **Assignment mechanism**: P(Treatment | Covariates)
  - Randomized: P(T|X) = P(T) (independent)
  - Observational: P(T|X) depends on X (confounding)
- **Treatment interaction**: Does treatment effect vary by entity?
  - Heterogeneous treatment effects: τᵢ = f(Xᵢ)

**C. Treatment-Outcome relations (Causal effects)**

**Classical approaches:**

1. **Mean difference**:
   - τ = E[Y | T=1] - E[Y | T=0]
   - Assumes: parallel trends, no confounding

2. **Regression framework**:
   - Y = β₀ + β₁T + β₂X + ε
   - Treatment effect: β₁

3. **Potential outcomes**:
   - Yᵢ(1) = outcome if treated
   - Yᵢ(0) = outcome if untreated  
   - ATE = E[Yᵢ(1) - Yᵢ(0)]

**Modern approaches:**

1. **Functional representation**:
   - Y = f(T, X, t) + ε
   - f learned via ML (neural nets, gradient boosting)

2. **Causal graphs (DAGs)**:
   ```
   T → M → Y  (mediation)
   X → T → Y  (confounding)
   T ← U → Y  (unobserved confounding)
   ```
   - Identify confounders via d-separation
   - Estimate causal effects via do-calculus

3. **Structural Causal Models (SCM)**:
   - T := f_T(X, U_T)
   - Y := f_Y(T, M, U_Y)
   - Counterfactual interventions: do(T=t)

4. **Time-varying treatment**:
   - T(t), Y(t) as stochastic processes
   - Marginal structural models
   - G-methods (g-formula, g-estimation)

**D. Treatment-Treatment relations (Combination/interaction)**
- **Additive**: Y = f(T₁) + f(T₂)
- **Interactive**: Y = f(T₁, T₂) with synergy
- **Sequential**: T₂ depends on response to T₁ (adaptive designs)

**Step 5: Effect Quantification**

**Magnitude measures:**
- **Absolute difference**: Δ = Ȳ_treatment - Ȳ_control
- **Relative difference**: RR = Ȳ_treatment / Ȳ_control
- **Standardized**: Cohen's d = Δ / σ_pooled
- **Number needed to treat (NNT)**: 1 / (P_response_T - P_response_C)

**Statistical significance:**
- Hypothesis testing: H₀: τ = 0
- Confidence intervals: CI₉₅% = [τ̂ - 1.96·SE, τ̂ + 1.96·SE]
- Bayesian: Posterior P(τ > 0 | Data)

**Clinical significance:**
- Reliable Change Index (RCI)
- Minimal clinically important difference (MCID)
- Remission rates, response rates

**Formal Teaching Structure:**

```
Operationalization-Framework/
├── 01-entity-recognition.tex          # Identify & classify entities
├── 02-entity-quantification.tex       # E → ℝⁿ mappings
│   ├── categorical-variables
│   ├── continuous-variables
│   └── latent-constructs
├── 03-action-formalization.tex        # Treatment as T(t), vectors, sets
├── 04-relation-modeling.tex           # All pairwise relations
│   ├── entity-entity (correlation)
│   ├── entity-treatment (assignment)
│   ├── treatment-outcome (causation)
│   └── treatment-treatment (interaction)
├── 05-causal-frameworks.tex           # Potential outcomes, DAGs, SCM
├── 06-effect-quantification.tex       # Statistical + clinical significance
├── 07-classical-methods.tex           # t-tests, ANOVA, regression
├── 08-modern-methods.tex              # Causal ML, do-calculus
└── 09-integration.tex                 # When to use what
```

**Is this the level of formalization you're seeking? Should we develop concrete mathematical notation for each step?**


philosophical foundation for operationalization. Let me compare the two approaches:
Philosophical Hierarchy (Top-down)

Ontology → What exists? (metaphysics)
Epistemology → How do we know? (measurement theory)
Methodology → How do we study? (causal inference framework)
Statistics → How do we quantify? (estimation)

Our Conceptual Hierarchy

Entity recognition ≈ Ontology (what exists in our research domain)
Entity quantification ≈ Measurement model (concept → observable)
Action formalization ≈ Action encoding (intervention operationalization)
Relation modeling ≈ Structural relations (dependencies)
Effect quantification ≈ Estimand definition (what we estimate)

We're essentially the same, but with different emphasis!
The philosophical approach is more theory-driven (deductive):

Start from abstract ontological commitments
Work down to concrete measurements

Our approach is more pragmatic (iterative):

Start from RQ
Systematically formalize each component
Build up to full specification

Exactly! You've identified a **philosophical foundation** for operationalization. Let me compare the two approaches:

**Philosophical Hierarchy (Top-down)**
1. **Ontology** → What exists? (metaphysics)
2. **Epistemology** → How do we know? (measurement theory)
3. **Methodology** → How do we study? (causal inference framework)
4. **Statistics** → How do we quantify? (estimation)

**Our Conceptual Hierarchy**
1. **Entity recognition** ≈ Ontology (what exists in our research domain)
2. **Entity quantification** ≈ Measurement model (concept → observable)
3. **Action formalization** ≈ Action encoding (intervention operationalization)
4. **Relation modeling** ≈ Structural relations (dependencies)
5. **Effect quantification** ≈ Estimand definition (what we estimate)

**We're essentially the same, but with different emphasis!**

The philosophical approach is more **theory-driven** (deductive):
- Start from abstract ontological commitments
- Work down to concrete measurements

Our approach is more **pragmatic** (iterative):
- Start from RQ
- Systematically formalize each component
- Build up to full specification

**Unified Framework for Teaching:**

```
Formal Operationalization Framework
│
├── Level 1: ONTOLOGY
│   ├── What entities exist in our domain?
│   │   - Populations, interventions, outcomes, contexts
│   ├── What properties do they have?
│   │   - Intrinsic vs relational properties
│   ├── What relations exist between them?
│   │   - Causal, correlational, compositional
│   └── Philosophical foundations
│       - Realism vs constructivism
│       - Observable vs latent constructs
│
├── Level 2: MEASUREMENT MODEL
│   ├── Concept → Operational mapping
│   │   - Validity: Does it measure what we intend?
│   │   - Reliability: Is it consistent?
│   ├── Classical measurement theory
│   │   - Psychometrics: CTT, IRT
│   │   - Scale development
│   ├── Modern measurement approaches
│   │   - Multimodal measurement
│   │   - Behavioral/digital phenotyping
│   └── Latent variable models
│       - Factor analysis, SEM
│
├── Level 3: ACTION ENCODING
│   ├── How do we represent interventions?
│   │   - Discrete (on/off)
│   │   - Continuous (dose-response)
│   │   - Multidimensional (components)
│   ├── Time structure
│   │   - Point treatment vs sustained
│   │   - Time-varying treatment
│   ├── Treatment fidelity
│   │   - Implementation measurement
│   │   - Adherence quantification
│   └── Classical vs modern
│       - Manualized protocols vs adaptive
│
├── Level 4: STRUCTURAL RELATIONS
│   ├── Dependency specification
│   │   - Causal DAGs
│   │   - Structural equation models
│   ├── Confounding structure
│   │   - Backdoor paths
│   │   - Adjustment sets
│   ├── Mediation/moderation
│   │   - Indirect effects
│   │   - Effect heterogeneity
│   └── Assumptions
│       - Ignorability, SUTVA, positivity
│
└── Level 5: ESTIMAND DEFINITION
    ├── What exactly are we estimating?
    │   - ATE, ATT, CATE
    │   - Statistical vs causal
    ├── Target population
    │   - Sample vs population
    │   - Generalizability
    ├── Identification
    │   - Is estimand identifiable from data?
    │   - What assumptions required?
    └── Classical vs modern
        - Parametric assumptions vs nonparametric
```

**The Key Insight:**

Both approaches recognize that **operationalization is not just "pick a measure"** - it requires:
1. **Philosophical clarity** about what exists (ontology)
2. **Measurement theory** to map concepts to data
3. **Formal specification** of causal structures
4. **Mathematical precision** in defining estimands

**For teaching:**

We should probably start with the **philosophical foundation** to give students the "why":
- Why does ontology matter? (Garbage in, garbage out)
- Why can't we just "measure depression"? (Construct validity)
- Why do we need DAGs? (Confounding, causal identification)

Then move to the **practical workflow**:
- Given RQ → Extract entities → Formalize → Quantify → Estimate

**Teaching module revision:**

```
Research-Design-Fundamentals/
├── 01-philosophical-foundations.tex
│   ├── ontology-in-social-science
│   ├── measurement-theory
│   └── causation-vs-correlation
├── 02-from-RQ-to-ontology.tex
│   ├── entity-identification
│   ├── property-specification
│   └── relation-mapping
├── 03-measurement-models.tex
│   ├── classical-psychometrics
│   ├── modern-measurement
│   └── validity-reliability
├── 04-action-encoding.tex
│   ├── intervention-formalization
│   ├── treatment-heterogeneity
│   └── fidelity-measurement
├── 05-structural-specification.tex
│   ├── causal-graphs (DAGs)
│   ├── potential-outcomes
│   └── structural-causal-models
├── 06-estimand-definition.tex
│   ├── what-are-we-estimating
│   ├── identification-assumptions
│   └── target-population
└── 07-integration-workflow.tex
    └── complete-example: RQ → estimand
```

**Does this unified framework capture what you're thinking? Should we develop this from the philosophical top-down, or from the practical bottom-up, or both simultaneously?**


在操作化后呢？I think we comes to the most serious and challenging points. We may (1)design experiment, if based of experiment, (2) design literature collection, and measurement, evaluation way if is it a literature reviw or document analyze research scheme, (3)design survey, if it is a survey based schemes, (4)...


这是一个**非常关键、而且你已经站在“真正做研究”的入口处**的问题。

你说得完全对：
**操作化完成之后，真正困难、也真正分叉的地方才开始。**

下面我会用一个**严格、可教、可写进教材**的方式来回答你，而不是给一个杂乱的“方法列表”。

---

## 一句话总览（先给结论）

> **操作化之后，不是“选方法”，而是“选择研究方案（research scheme）”。**
> 不同研究方案，对应的是**不同的证据生成逻辑（evidence-generating logic）**。

你列的 (1)(2)(3) 正是**不同 research scheme 的入口**。

---

## 一、操作化之后，研究进入哪一个“阶段”？

在我们前面建立的体系中：

* **操作化（operationalization）**
  → 已经明确了

  * 实体
  * 测量
  * 行动
  * 关系
  * 效应（estimand）

接下来进入的不是“统计阶段”，而是：

> **研究设计阶段（Research Design / Evidence Design）**

核心问题从

> *“我在研究什么？”*
> 转变为
> **“我如何生成可信证据来回答它？”**

---

## 二、一个关键的总分叉：证据从哪里来？

操作化之后，**第一道不可回避的总分叉**是：

> **证据是“主动生成”的，还是“被动整理”的？**

这决定了你后面所有设计逻辑。

---

## 三、主要 research schemes（你列得已经非常对）

下面我把你提到的 (1)(2)(3) 放进一个**统一框架**里。

---

### （1）实验 / 准实验方案

**Experiment-based schemes**

#### 什么时候走这条路？

* RQ 明确是 **因果问题**
* 行动（treatment）**可以被控制或准控制**
* 有伦理与资源许可

#### 核心设计任务（不是统计！）

1. **处理分配机制**

   * 随机？
   * 准随机？
   * 自然实验？
2. **对照条件**

   * 无处理？
   * 等待名单？
   * treatment-as-usual？
3. **时间结构**

   * 前后测？
   * 多时间点？
4. **威胁控制**

   * 混杂
   * 溢出效应
   * 不依从（non-compliance）

👉 这一步本质上是在回答：

> **“如果我想主张因果，我愿意承担哪些假设？”**

---

### （2）文献综述 / 文献计量 / 文本分析方案

**Literature-based / document-based schemes**

你这里的判断**非常专业**：
文献综述不是“前期工作”，而是**一种独立 research scheme**。

#### 核心问题不是“收集多少文献”，而是：

1. **证据单位是什么？**

   * 论文？
   * 实验？
   * 结论？
2. **纳入 / 排除标准**

   * 时间
   * 方法
   * 数据类型
3. **测量与编码方案**

   * 定性编码？
   * 定量指标？
   * 自动文本分析？
4. **评估逻辑**

   * 描述性？
   * 关联性？
   * 证据一致性？

👉 这是在回答：

> **“已有知识在多大程度上支持 / 不支持这个 RQ？”**

而不是“我怎么看文献”。

---

### （3）调查（Survey-based schemes）

#### 什么时候走这条路？

* 实体是**个体/群体**
* 行为、态度、感知不可直接观测
* 实验不可行或不伦理

#### 操作化之后，你必须进一步设计：

1. **抽样逻辑**

   * 目标总体是什么？
   * 推断到哪里？
2. **测量工具**

   * 量表构建
   * 信度 / 效度
3. **问卷结构**

   * 顺序效应
   * 反应偏差
4. **推断边界**

   * 描述？
   * 关联？
   * 因果（非常谨慎）？

👉 本质问题是：

> **“从主观报告，我最多能推出什么结论？”**

---

### （4）你没写出来，但必须补充的几类

这是教材里**一定要有的完整性**。

#### （4a）二手数据 / 行政数据分析

* 数据已存在
* 操作化必须**反向适配数据**
* 核心是可识别性（identifiability）

#### （4b）混合方法（Mixed schemes）

* 定量 + 定性
* 调查 + 实验
* 文献 + 数据分析

#### （4c）模拟 / 生成型方案

* Agent-based model
* 机制模拟
* 理论可行性验证

---

## 四、真正的“严肃点”：不是选方案，而是**方案—RQ 匹配**

你现在已经到了一个**非常高级**的认识层级：

> **不是每个 RQ 都“配得上”每种 research scheme。**

操作化之后，必须问三个残酷问题：

1. **这个 RQ 在这个 scheme 下还能成立吗？**
2. **结论能回答原始 RQ 的哪一部分？**
3. **哪些主张我必须主动放弃？**

这一步叫：

> **inferential humility（推断谦抑）**

---

## 五、一个非常重要的教学观点（你会很适合讲）

> **研究方案不是技术选择，而是“承诺管理（assumption management）”。**

* 实验：承诺伦理 + 控制
* 调查：承诺测量 + 外推限制
* 文献分析：承诺既有研究质量
* 二手数据：承诺不可控生成过程

---

## 六、可以直接写进教材的一段总结

你可以几乎原封不动地这样写：

> 在完成研究问题的操作化之后，研究者并未进入统计分析阶段，而是进入了研究方案选择阶段。不同研究方案代表着不同的证据生成机制，它们决定了研究者可以主张何种类型的结论、需要承担何种假设、以及必须接受哪些推断边界。实验、调查、文献分析等方案并非可互换工具，而是与研究问题在逻辑上相互约束的认识路径。

---

## 七、下一步如果你愿意继续深入

我们可以非常自然地继续到：

* **RQ → scheme 匹配矩阵**
* **“哪些 RQ 不应该用实验 / 调查 / ML”**
* **从 scheme 到 estimation strategy 的过渡**
* **为什么很多 DL 论文在 scheme 层面已经失败**

你现在已经在**方法论核心区**了。

你想下一步往哪一个方向推进？


精确！操作化之后，就是**研究设计的核心决策** - 选择什么样的数据收集和分析策略。这是最关键的分叉点。

**Research Design Taxonomy (Post-Operationalization)**

```
After Operationalization → Design Strategy Selection
│
├── 1. EXPERIMENTAL DESIGNS
│   ├── Randomized Controlled Trials (RCT)
│   │   ├── Parallel group design
│   │   ├── Crossover design
│   │   ├── Factorial design (2×2, 2×3, etc.)
│   │   └── Cluster randomized trials
│   ├── Quasi-Experimental
│   │   ├── Natural experiments
│   │   ├── Difference-in-differences
│   │   ├── Regression discontinuity
│   │   ├── Interrupted time series
│   │   └── Instrumental variables
│   └── Lab Experiments
│       ├── Controlled laboratory settings
│       ├── Online experiments (A/B testing)
│       └── Behavioral economics experiments
│
├── 2. SURVEY-BASED DESIGNS
│   ├── Cross-sectional surveys
│   │   ├── One-time measurement
│   │   ├── Sampling strategy (probability/non-probability)
│   │   └── Survey modes (online, phone, face-to-face)
│   ├── Longitudinal surveys
│   │   ├── Panel studies (same individuals over time)
│   │   ├── Cohort studies (birth cohort, age cohort)
│   │   └── Repeated cross-sections (different samples, same population)
│   └── Mixed-mode surveys
│       └── Combining multiple data collection methods
│
├── 3. OBSERVATIONAL DESIGNS
│   ├── Prospective observational
│   │   ├── Cohort studies (follow forward in time)
│   │   └── Case-control studies (compare groups retrospectively)
│   ├── Retrospective analysis
│   │   ├── Medical records, administrative data
│   │   └── Historical data analysis
│   └── Ecological studies
│       └── Aggregate-level analysis (countries, regions)
│
├── 4. LITERATURE-BASED DESIGNS (Secondary Research)
│   ├── Systematic literature review
│   │   ├── PRISMA protocol
│   │   ├── Inclusion/exclusion criteria
│   │   ├── Search strategy (databases, keywords)
│   │   └── Quality assessment of studies
│   ├── Meta-analysis
│   │   ├── Effect size extraction
│   │   ├── Heterogeneity assessment (I², Q-statistic)
│   │   ├── Fixed vs random effects models
│   │   └── Publication bias detection (funnel plots)
│   ├── Scoping review
│   │   └── Exploratory mapping of literature
│   └── Narrative review
│       └── Interpretive synthesis
│
├── 5. DOCUMENT/TEXT ANALYSIS DESIGNS
│   ├── Content analysis
│   │   ├── Classical: Manual coding with reliability checks
│   │   ├── Modern: Automated text classification (NLP)
│   │   └── Mixed: Human-in-the-loop annotation
│   ├── Discourse analysis
│   │   ├── Conversation analysis
│   │   ├── Critical discourse analysis
│   │   └── Frame analysis
│   ├── Historical document analysis
│   │   ├── Archival research
│   │   └── Historical comparative methods
│   └── Computational text analysis
│       ├── Topic modeling (LDA, STM)
│       ├── Sentiment analysis
│       ├── Word embeddings
│       └── Network analysis of texts
│
├── 6. CASE STUDY DESIGNS
│   ├── Single case design
│   │   ├── In-depth, idiographic analysis
│   │   └── Theory building
│   ├── Multiple case design
│   │   ├── Cross-case comparison
│   │   └── Replication logic
│   └── Embedded case design
│       └── Multiple units of analysis within case
│
├── 7. MIXED METHODS DESIGNS
│   ├── Sequential designs
│   │   ├── Exploratory: Qualitative → Quantitative
│   │   └── Explanatory: Quantitative → Qualitative
│   ├── Concurrent designs
│   │   ├── Convergent: Both simultaneously, compare results
│   │   └── Embedded: One method within the other
│   └── Transformative designs
│       └── Advocacy/participatory frameworks
│
├── 8. SECONDARY DATA ANALYSIS
│   ├── Existing survey data (NHANES, GSS, ANES, etc.)
│   ├── Administrative records
│   │   ├── Health records (EMR/EHR)
│   │   ├── Educational data (grades, attendance)
│   │   └── Government databases (census, tax records)
│   ├── Big data sources
│   │   ├── Social media (Twitter, Reddit, Facebook)
│   │   ├── Digital traces (web logs, search queries)
│   │   ├── Sensor data (mobile, wearables, IoT)
│   │   └── Transaction data (credit cards, e-commerce)
│   └── Open science data repositories
│
├── 9. COMPUTATIONAL/SIMULATION DESIGNS
│   ├── Agent-based modeling (ABM)
│   ├── System dynamics modeling
│   ├── Network simulations
│   ├── Monte Carlo simulations
│   └── Digital twin experiments
│
└── 10. EMERGING/HYBRID DESIGNS
    ├── Citizen science designs
    ├── Crowdsourced research
    ├── Ecological momentary assessment (EMA)
    ├── Experience sampling methods (ESM)
    ├── Digital phenotyping
    └── Passive sensing studies
```

**Decision Framework: Which Design to Choose?**

```
Design Selection Criteria:

1. Research Question Type
   - Causal (does X cause Y?) → Experimental/Quasi-experimental
   - Descriptive (what is prevalence?) → Survey/Observational
   - Exploratory (what patterns exist?) → Mixed methods/Case study
   - Synthesis (what do we know?) → Literature review/Meta-analysis

2. Feasibility Constraints
   - Time: Longitudinal possible? Or cross-sectional only?
   - Budget: Can afford RCT? Or use secondary data?
   - Ethics: Can randomize? Or must be observational?
   - Access: Can recruit participants? Or analyze existing data?

3. Data Characteristics
   - Structured (numbers, categories) → Quantitative designs
   - Unstructured (text, images) → Qualitative/Computational text
   - Both → Mixed methods
   - Big/messy → Computational approaches

4. Epistemological Position
   - Positivist → Experimental, quantitative
   - Interpretivist → Qualitative, case study
   - Pragmatist → Mixed methods
   - Critical → Participatory, transformative

5. Existing Knowledge Base
   - Mature field → Confirmatory RCT, meta-analysis
   - Emerging field → Exploratory, mixed methods
   - Contradictory findings → Systematic review, replication
```

**Teaching Module Structure:**

```
03-research-design-strategies/
├── 00-design-selection-framework.tex
│   ├── decision-tree for choosing design
│   ├── trade-offs matrix
│   └── feasibility checklist
│
├── 01-experimental-designs/
│   ├── classical-RCT.tex
│   ├── quasi-experimental.tex
│   ├── factorial-designs.tex
│   └── modern-online-experiments.tex
│
├── 02-survey-designs/
│   ├── cross-sectional.tex
│   ├── longitudinal-panel.tex
│   ├── sampling-strategies.tex
│   └── survey-modes.tex
│
├── 03-observational-designs/
│   ├── cohort-studies.tex
│   ├── case-control.tex
│   └── administrative-data.tex
│
├── 04-literature-synthesis/
│   ├── systematic-review.tex
│   ├── meta-analysis.tex
│   └── scoping-review.tex
│
├── 05-text-document-analysis/
│   ├── classical-content-analysis.tex
│   ├── computational-text-mining.tex
│   └── mixed-approaches.tex
│
├── 06-case-study-designs/
│   ├── single-case.tex
│   ├── comparative-case.tex
│   └── process-tracing.tex
│
├── 07-mixed-methods/
│   ├── sequential-designs.tex
│   ├── concurrent-designs.tex
│   └── integration-strategies.tex
│
├── 08-secondary-big-data/
│   ├── existing-survey-data.tex
│   ├── administrative-records.tex
│   ├── social-media-data.tex
│   └── digital-traces.tex
│
├── 09-computational-simulation/
│   ├── agent-based-models.tex
│   ├── network-simulation.tex
│   └── digital-twins.tex
│
└── 10-integration-examples/
    ├── same-RQ-multiple-designs.tex
    ├── combining-designs.tex
    └── design-justification.tex
```

**Key Teaching Approach:**

For **each design type**, teach:
1. **Conceptual logic** - Why this design?
2. **Classical implementation** - Traditional approach
3. **Modern variants** - Computational/digital innovations
4. **Strengths & limitations** - Trade-offs
5. **When to use** - Decision criteria
6. **Worked example** - Complete walkthrough

**这个分类是否完整？还需要补充哪些研究设计类型？**

Cohort 和 Longitudinal 通常不是实验设计，而是观察性研究设计
真正的实验设计 (Experimental Designs) 需要研究者主动操控/分配干预条件



研究设计的三条核心维度（先给总框架）

任何经验研究设计，都可以从至少 三条正交维度来描述：

维度 A：是否操控干预？

实验（Experimental）

观察（Observational）

维度 B：时间结构？

横断（Cross-sectional）

纵向（Longitudinal）

维度 C：研究单位如何形成？

个体水平

群体 / 队列（Cohort）

面板（Panel）

你听到的 cohort、longitudinal，其实是 B / C 维度的术语，不是“方法本身”。




Amazing! You help me alot. So we have different dimension to describe a research method, according them , we classifiy to different kinds of scheme. cohort

longitudinal

cross-sectional just dimensions, and something like observational, experimental schemes are the schemes classirify on the top of them

Dimension --> Schme.





完全正确！你抓住了关键 - **维度 (dimensions)** vs **方案 (schemes)** 的区别。让我系统化这个分类框架：

---

## **研究设计的多维度分类框架**

### **核心思想：**
研究设计不是单一分类，而是**多个维度的组合**。每个维度有不同的取值，组合起来形成具体的研究方案。

---

## **维度 (Dimensions) - 描述性特征**

### **维度 1: 时间结构 (Temporal Structure)**
```
取值：
├── Cross-sectional (横断面)
│   └── 单一时间点测量
│
├── Longitudinal (纵向)
│   ├── 多个时间点测量
│   └── 子类型：
│       ├── Prospective (前瞻性) - 向前跟踪
│       ├── Retrospective (回溯性) - 回顾历史
│       └── Ambispective (双向) - 结合前瞻和回溯
│
└── Time-series (时间序列)
    └── 密集、连续的时间点测量
```

### **维度 2: 干预性质 (Intervention Nature)**
```
取值：
├── Experimental (实验性)
│   └── 研究者主动操控/分配干预
│
├── Quasi-experimental (准实验性)
│   └── 有干预但无随机分配
│
└── Observational (观察性)
    └── 无任何干预，纯观察
```

### **维度 3: 分配机制 (Assignment Mechanism)**
```
取值：
├── Randomized (随机化)
│   ├── Individual randomization (个体随机)
│   ├── Cluster randomization (整群随机)
│   └── Stratified randomization (分层随机)
│
├── Non-randomized but controlled (非随机但受控)
│   ├── Matching
│   ├── Propensity score
│   └── Regression adjustment
│
└── Natural/Self-selection (自然选择)
    └── 个体自主决定是否暴露
```

### **维度 4: 样本跟踪 (Sample Tracking)**
```
取值：
├── Same individuals (同一批个体)
│   ├── Cohort (队列) - 基于共同特征招募
│   └── Panel (面板) - 重复测量同一批人
│
├── Different individuals (不同个体)
│   ├── Repeated cross-sections (重复横断面)
│   └── Independent samples (独立样本)
│
└── Mixed (混合)
    └── 部分overlap，部分新增
```

### **维度 5: 数据来源 (Data Source)**
```
取值：
├── Primary data (一手数据)
│   ├── Self-collected (研究者自己收集)
│   └── Purpose-built (为研究目的专门设计)
│
├── Secondary data (二手数据)
│   ├── Administrative records (行政记录)
│   ├── Existing surveys (现有调查)
│   └── Big data (大数据)
│
└── Mixed (混合)
    └── 结合一手和二手数据
```

### **维度 6: 方向性 (Directionality)**
```
取值：
├── Prospective (前瞻)
│   └── 从暴露到结局（向前）
│
├── Retrospective (回溯)
│   └── 从结局到暴露（向后）
│
└── Cross-sectional (同时)
    └── 暴露和结局同时测量
```

### **维度 7: 对照类型 (Control Type)**
```
取值：
├── Between-subjects (组间)
│   └── 不同个体接受不同条件
│
├── Within-subjects (组内/个体内)
│   └── 同一个体接受不同条件
│
├── Mixed (混合)
│   └── 同时有组间和组内因素
│
└── No control (无对照)
    └── 单组前后对比
```

### **维度 8: 比较基准 (Comparison Basis)**
```
取值：
├── Experimental control (实验对照)
│   ├── Placebo
│   ├── Waitlist
│   ├── Treatment as usual (TAU)
│   └── Active control
│
├── Historical control (历史对照)
│   └── 使用过去的数据作为对照
│
├── External control (外部对照)
│   └── 不同population的对照组
│
└── Self-control (自身对照)
    └── 个体作为自己的对照
```

---

## **方案 (Schemes) - 维度的组合**

具体的研究方案 = **多个维度的特定组合**

### **例子 1: Randomized Controlled Trial (RCT)**
```
维度组合：
├── 时间结构: Longitudinal (pre-post)
├── 干预性质: Experimental
├── 分配机制: Randomized (individual)
├── 样本跟踪: Same individuals
├── 数据来源: Primary data
├── 方向性: Prospective
├── 对照类型: Between-subjects
└── 比较基准: Experimental control (placebo/waitlist)
```

### **例子 2: Prospective Cohort Study**
```
维度组合：
├── 时间结构: Longitudinal
├── 干预性质: Observational
├── 分配机制: Natural/Self-selection
├── 样本跟踪: Cohort (same individuals with shared characteristic)
├── 数据来源: Primary or secondary
├── 方向性: Prospective
├── 对照类型: Between-subjects (exposed vs unexposed)
└── 比较基准: Natural comparison groups
```

### **例子 3: Difference-in-Differences (DiD)**
```
维度组合：
├── 时间结构: Longitudinal (at least 2 time points)
├── 干预性质: Quasi-experimental
├── 分配机制: Non-randomized (natural experiment)
├── 样本跟踪: Can be same or different individuals
├── 数据来源: Often secondary data
├── 方向性: Prospective
├── 对照类型: Between-subjects (treatment vs control regions/groups)
└── 比较基准: Parallel trends assumption
```

### **例子 4: Crossover RCT**
```
维度组合：
├── 时间结构: Longitudinal (multiple periods)
├── 干预性质: Experimental
├── 分配机制: Randomized (order of treatments)
├── 样本跟踪: Same individuals
├── 数据来源: Primary data
├── 方向性: Prospective
├── 对照类型: Within-subjects (each person gets all treatments)
└── 比较基准: Self-control + experimental control
```

### **例子 5: Case-Control Study**
```
维度组合：
├── 时间结构: Cross-sectional (at recruitment) with retrospective exposure
├── 干预性质: Observational
├── 分配机制: Natural/Self-selection
├── 样本跟踪: Different selection (cases vs controls)
├── 数据来源: Often secondary + retrospective primary
├── 方向性: Retrospective
├── 对照类型: Between-subjects (cases vs controls)
└── 比较基准: Matched or unmatched controls
```

---

## **教学框架：多维度视角**

### **教学结构建议：**

```
Module: Research Design Classification Framework

Part 1: Understanding Dimensions (理解维度)
├── 01-temporal-dimension.tex
│   ├── Cross-sectional vs longitudinal
│   ├── Time-series
│   └── When time matters
│
├── 02-intervention-dimension.tex
│   ├── Experimental vs observational
│   ├── Quasi-experimental as middle ground
│   └── Causal inference implications
│
├── 03-assignment-dimension.tex
│   ├── Randomization and its types
│   ├── Non-random assignment strategies
│   └── Selection bias considerations
│
├── 04-tracking-dimension.tex
│   ├── Cohort vs panel vs repeated cross-sections
│   ├── Same vs different individuals
│   └── Attrition and retention
│
├── 05-data-source-dimension.tex
│   ├── Primary vs secondary
│   ├── Trade-offs
│   └── Data quality considerations
│
├── 06-directionality-dimension.tex
│   ├── Prospective vs retrospective
│   ├── Temporal ordering
│   └── Bias implications
│
├── 07-control-dimension.tex
│   ├── Between vs within subjects
│   ├── Statistical power implications
│   └── Carry-over effects
│
└── 08-comparison-dimension.tex
    ├── Types of control groups
    ├── Ethical considerations
    └── Validity trade-offs

Part 2: Common Design Schemes (常见方案)
├── 09-scheme-as-combinations.tex
│   └── How dimensions combine to form designs
│
├── 10-experimental-schemes.tex
│   ├── RCT variants (parallel, crossover, factorial)
│   ├── Cluster trials
│   └── Adaptive designs
│
├── 11-quasi-experimental-schemes.tex
│   ├── DiD, RDD, ITS, IV
│   └── Natural experiments
│
├── 12-observational-schemes.tex
│   ├── Cohort studies
│   ├── Case-control studies
│   ├── Panel studies
│   └── Cross-sectional surveys
│
└── 13-hybrid-schemes.tex
    └── Combinations and innovations

Part 3: Design Selection (设计选择)
├── 14-dimension-decision-tree.tex
│   └── Systematic approach to choosing dimensions
│
├── 15-constraint-mapping.tex
│   ├── Ethical constraints → dimension choices
│   ├── Resource constraints → dimension choices
│   └── Feasibility constraints → dimension choices
│
└── 16-worked-examples.tex
    └── Same RQ, different dimensional combinations
```

---

## **可视化：多维空间中的设计方案**

```
想象一个多维空间，每个维度是一个轴：

Axis 1: Time (Cross-sectional ←→ Longitudinal)
Axis 2: Intervention (Observational ←→ Experimental)
Axis 3: Assignment (Natural ←→ Randomized)
Axis 4: Tracking (Different ←→ Same individuals)
...

每个具体的研究设计 = 这个多维空间中的一个点

例如：
- RCT = (Longitudinal, Experimental, Randomized, Same, Primary, Prospective, Between, Experimental control)
- Cohort = (Longitudinal, Observational, Natural, Same, Mixed, Prospective, Between, Natural comparison)
```

---

## **教学优势：**

### **1. 概念清晰**
- 学生理解："Cohort" 不是一种设计方案，而是**样本跟踪维度**的一个取值
- "Longitudinal" 是**时间维度**的一个取值
- "RCT" 是多个维度的特定组合

### **2. 灵活组合**
- 学生可以创造性地组合维度
- 例如："Longitudinal cohort RCT" = RCT + Cohort tracking + Long-term follow-up
- "Retrospective case-control with matching" = Case-control + Retrospective + Matched assignment

### **3. 批判性思维**
- 理解每个维度选择的trade-offs
- 不同维度组合如何影响因果推断强度
- 为什么某些组合不可行（例如：Randomized + Retrospective 矛盾）

### **4. 系统化决策**
- 给定RQ和约束条件
- 逐个维度做决策
- 最终得到完整的研究设计方案

---

**这个多维框架是否符合你的理解？需要进一步细化哪些维度或方案？**


Excellent—this is exactly the right moment to **freeze the framework**, summarize it cleanly, and then **extend it in a principled way**. Below is a **canonical summary + controlled extension** that can serve as a reference model for teaching, writing, and design work.

---

# I. Core Thesis (One-Line)

> **Research designs are best understood as structured combinations of orthogonal dimensions; named research schemes are stable, interpretable regions in this multidimensional design space.**

---

# II. DIMENSIONS (Descriptive Axes)

These are **not methods**. They describe *how* a study is organized.

## 1. Intervention / Control Dimension

**Who controls exposure?**

| Value              | Description                                |
| ------------------ | ------------------------------------------ |
| Experimental       | Researcher actively assigns intervention   |
| Quasi-experimental | Intervention exists, assignment not random |
| Observational      | No manipulation                            |

> **Primary determinant of causal strength**

---

## 2. Assignment Mechanism

**Why does a unit receive exposure?**

| Value         | Description                |
| ------------- | -------------------------- |
| Randomized    | Pure random assignment     |
| Rule-based    | Thresholds, policies (RDD) |
| Natural       | External process           |
| Self-selected | Individual choice          |

---

## 3. Temporal Structure

**How is time treated?**

| Value           | Description             |
| --------------- | ----------------------- |
| Cross-sectional | One time point          |
| Longitudinal    | Multiple waves          |
| Time-series     | Dense repeated measures |

---

## 4. Unit Tracking

**Who is followed across time?**

| Value                   | Description                                 |
| ----------------------- | ------------------------------------------- |
| Cohort                  | Same individuals defined by entry condition |
| Panel                   | Same individuals, general sample            |
| Repeated cross-sections | Different individuals                       |

> **Cohort ≠ scheme**

---

## 5. Directionality

**Which temporal direction does inference follow?**

| Value         | Description        |
| ------------- | ------------------ |
| Prospective   | Exposure → outcome |
| Retrospective | Outcome → exposure |
| Simultaneous  | Measured together  |

---

## 6. Comparison Logic

**What plays the role of the counterfactual?**

| Value            | Description       |
| ---------------- | ----------------- |
| Between-subjects | Different groups  |
| Within-subjects  | Self as control   |
| Historical       | Past data         |
| External         | Other populations |

---

## 7. Data Provenance

**Where does the data come from?**

| Value     | Description               |
| --------- | ------------------------- |
| Primary   | Collected for this study  |
| Secondary | Administrative / archival |
| Mixed     | Combination               |

---

## 8. Measurement Intensity (Extension)

**How dense is measurement?**

| Value     | Description    |
| --------- | -------------- |
| Sparse    | Few indicators |
| Repeated  | Standard waves |
| Intensive | EMA / sensors  |

---

## 9. Adaptivity (Extension)

**Does the design evolve during the study?**

| Value         | Description           |
| ------------- | --------------------- |
| Fixed         | Fully pre-specified   |
| Adaptive      | Rules respond to data |
| Fully dynamic | Continuous updating   |

---

# III. SCHEMES (Named Configurations)

Schemes are **inferential templates**, not mere checklists.

---

## 1. Randomized Controlled Trial (RCT)

| Dimension    | Value             |
| ------------ | ----------------- |
| Intervention | Experimental      |
| Assignment   | Randomized        |
| Time         | Longitudinal      |
| Tracking     | Same units        |
| Direction    | Prospective       |
| Comparison   | Between or within |

**Claim Type:** Strong causal effect
**Core Assumption:** Randomization valid

---

## 2. Quasi-Experimental Designs

### Examples: DiD, RDD, ITS, IV

| Dimension    | Value                     |
| ------------ | ------------------------- |
| Intervention | Quasi-experimental        |
| Assignment   | Rule-based / natural      |
| Time         | Longitudinal              |
| Comparison   | Structured counterfactual |

**Claim Type:** Conditional causal inference
**Core Assumption:** Design-specific (parallel trends, continuity)

---

## 3. Prospective Cohort Study

| Dimension    | Value         |
| ------------ | ------------- |
| Intervention | Observational |
| Assignment   | Natural       |
| Time         | Longitudinal  |
| Tracking     | Cohort        |
| Direction    | Prospective   |

**Claim Type:** Risk / association
**Core Limitation:** Confounding

---

## 4. Case–Control Study

| Dimension    | Value             |
| ------------ | ----------------- |
| Intervention | Observational     |
| Assignment   | Outcome-based     |
| Direction    | Retrospective     |
| Comparison   | Cases vs controls |

**Claim Type:** Etiological association
**Core Risk:** Recall & selection bias

---

## 5. Cross-Sectional Survey

| Dimension    | Value            |
| ------------ | ---------------- |
| Intervention | Observational    |
| Time         | Cross-sectional  |
| Direction    | Simultaneous     |
| Comparison   | Between-subjects |

**Claim Type:** Description / correlation
**Not causal by default**

---

## 6. Panel Study

| Dimension    | Value            |
| ------------ | ---------------- |
| Intervention | Observational    |
| Time         | Longitudinal     |
| Tracking     | Same individuals |
| Comparison   | Within + between |

**Claim Type:** Change & dynamics
**Key Risk:** Attrition

---

## 7. Systematic Review / Meta-Analysis

| Dimension  | Value               |
| ---------- | ------------------- |
| Data       | Secondary           |
| Unit       | Studies             |
| Comparison | Synthesized effects |

**Claim Type:** Knowledge synthesis
**Assumption:** Study quality & comparability

---

## 8. Computational / Digital Trace Study (Extension)

| Dimension    | Value                    |
| ------------ | ------------------------ |
| Intervention | Observational            |
| Data         | Passive / high-frequency |
| Measurement  | Intensive                |
| Time         | Often time-series        |

**Claim Type:** Behavioral patterns
**Risk:** Construct validity

---

## 9. Adaptive / SMART Designs (Extension)

| Dimension    | Value        |
| ------------ | ------------ |
| Intervention | Experimental |
| Adaptivity   | Adaptive     |
| Time         | Longitudinal |
| Assignment   | Rule-based   |

**Claim Type:** Optimal treatment sequencing
**Complexity:** Design + analysis coupling

---

# IV. Dimension → Scheme Mapping (Key Insight)

```
Dimensions = building blocks
Schemes = recognizable structures
Inference = governed by the weakest dimension
```

> A design is only as strong as its **most fragile assumption**.

---

# V. Teaching-Ready Summary Table

| Term            | Ontological Status                |
| --------------- | --------------------------------- |
| Cohort          | Tracking dimension                |
| Longitudinal    | Temporal dimension                |
| Cross-sectional | Temporal dimension                |
| Experimental    | Intervention dimension            |
| Observational   | Intervention dimension            |
| RCT             | Research scheme                   |
| DiD             | Research scheme                   |
| Survey          | Data collection mode (not scheme) |

---

# VI. Final Canonical Statement (You Can Reuse This)

> Research schemes are not defined by single labels such as “cohort” or “longitudinal,” but by coherent combinations of multiple design dimensions. Understanding these dimensions allows researchers to construct, evaluate, and critique research designs systematically, rather than selecting methods by name.

---

# VII. Where to Extend Next (Optional)

Natural next expansions:

1. **Dimension–Estimand compatibility**
2. **Which dimensions dominate bias**
3. **Scheme failure diagnostics**
4. **Why ML often ignores scheme logic**

If you want, we can turn this into:

* a **formal ontology**
* a **decision algorithm**
* or a **full teaching chapter**

You’ve built something *very serious* here.
