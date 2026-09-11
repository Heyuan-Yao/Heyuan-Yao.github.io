---
permalink: /
title: "Welcome to Heyuan's Personal Website!"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a third-year Ph.D. student in the Department of Industrial Engineering & Management Sciences at Northwestern University. I am fortunately advised by Prof. <a href="https://isaacg1.github.io/">Izzy Grosof</a>. Till May 2024, I was in the Joint Bachelor’s Degree Program between City University of Hong Kong and Columbia University, where I was advised by Prof. <a href="https://www.columbia.edu/~vhd1/">Victor H. de la Peña</a> and Prof. <a href="https://www.math.columbia.edu/~ik/">Ioannis Karatzas</a>. I received my B.A. in Mathematics-Statistics from Columbia and B.Sc. in Computing Mathematics from CityU.

I am broadly interested in developing theory and methods for probability and statistics. My current interests include 
- Queueing theory, scheduling policies.
- Multiserver-/Multiresource- job (MSJ/MRJ) systems and caching systems, with applications to model computing systems, including datacenters, and LLM serving systems.
- Decoupling, concentration inequalities for random processes.
- Self-normalization, U-statistics.

Education
------
*Northwestern University, IL, USA: Ph.D. in Industrial Engineering and Management Sciences, Sep. 2024 - Now*

*Columbia University in the City of New York, NY, USA: Bachelor of Arts in Mathematics-Statistics, Sep. 2021 - May 2024*

*City University of Hong Kong, Hong Kong SAR: Bachelor of Science in Computing Mathematics, Sep. 2019 - May 2024*

Publications
------
<h4><a href="https://arxiv.org/pdf/2512.19063">Sharp Decoupling Inequalities for the Variances and Second Moments of Sums of Dependent Random Variables</a>, V.H. de la Peña, H. Yao, D. Alemayehu, V.K. de la Peña (2026), Electronic Communications in Probability.</h4>
<h4> <a href="https://isaacg1.github.io/assets/scaling-cycles-short.pdf">Non-preemptive Datacenter Scheduling via Scaling Cycles</a>, Z. Chen, H. Yao, I. Grosof, B. Berg (2026), The MAMA workshop at ACM SIGMETRICS 2026. </h4>
<h4><a href="https://www.sciencedirect.com/science/article/pii/S0167715226001185">A Scalable Formula for the Moments of a Family of Self-Normalized Statistics</a>, H. Zou, H. Yao, V.H. de la Peña (2026), Statistics & Probability Letters. </h4>
<h4><a href="https://www.sciencedirect.com/science/article/pii/S0167715225000215">Unbiased estimation of the Gini coefficient</a>, B. Baydil, V.H. de la Peña, H. Zou, H. Yao (2025), Statistics & Probability Letters. </h4>

Preprints
------
<h4><a href="https://arxiv.org/abs/2609.02027">Multi-Turn LLM Conversations under the Least-Recently-Used Policy: Mean-Field Asymptotics and Hit Ratio Approximation </a>, H. Yao, C. Gao, Y. Lyu, I. Grosof, D. Simchi-Levi (2026), Workshop Version Submitted. </h4>
<h4><a href="https://arxiv.org/abs/2605.21715">Throughput-Optimal Multiresource-Job Scheduling with Continuous Requirement Distribution </a>, H. Yao, W. Kowalik, I. Grosof (2026), Submitted. </h4>

Some Project Ideas and Ongoing Projects
------
Last updated: Sep. 11, 2026.

**You can find several exciting open problems on multiserver-job (MSJ) and multiresource-job (MRJ) scheduling on <a href="https://isaacg1.github.io/project-ideas/">my advisor Izzy Grosof’s project ideas page</a>.** Some ideas that I am working on or actively pursuing are listed below. If you are interested in any of the open projects described here, please feel free to contact either Izzy or me.

<h3>[Ongoing] MSJ with varying resource requirements</h3>

I am working on an MSJ scheduling problem in which each job’s resource requirement varies over time. This setting captures an important feature of modern LLM serving systems: a conversation's memory footprint can jump when a new prompt arrives during prefilling and then grow token by token (as in SGLang) or block by block (as in vLLM) during decoding. I am working on this project with Izzy and <a href="https://chutonggao.github.io/">Chutong Gao</a>.

<h3>[Actively Pursuing] Can First-Fit Be Throughput-Optimal?</h3>

In our <a href="https://arxiv.org/abs/2605.21715">recent work</a> on multiresource-job (MRJ) scheduling, we study two special settings of the multiserver-job (MSJ) model. In both settings, service times are i.i.d. exponential, while job resource requirements are drawn from either a continuous symmetric distribution or a distribution with a decreasing density. In our numerical experiments, First-Fit achieves mean response times remarkably close to our K-Discretized Efficient MaxWeight (K-EMW) family of policies, a class of computationally lightweight policies that we prove to be throughput-optimal. We conjecture that First-Fit is also throughput-optimal in both settings. Near the stability boundary, First-Fit may not match the mean-response-time performance of K-EMW, but we believe that it can still stabilize the system under every stabilizable load.

A <a href="https://link.springer.com/content/pdf/10.1007/BF02679614.pdf">classic and elegant paper</a> by Coffman and Stolyar establishes a closely related result: when resource requirements follow a discrete symmetric distribution, both First-Fit and Best-Fit are throughput-optimal. Izzy and I successfully adapted their proof, together with an implicit discretization method, to establish the throughput optimality of First-Fit and Best-Fit under continuous symmetric distributions. The case of a continuous decreasing density, however, remains unresolved. I have spent several months exploring different proof strategies without success, and the attempted approaches are too numerous to summarize here. If you find this problem interesting, I would be delighted to collaborate with you, whether to prove the conjecture or construct a counterexample.

ps: One might question whether assuming identically distributed service times for jobs of different sizes is realistic. This setting matches naturally in LLM serving. During prefilling, GPUs or NPUs batch different numbers of prompt tokens for parallel processing within an iteration. Once the iteration is completed, the corresponding KV states have been generated leaves the prefiller (in the Prefill-Decode disaggregation setting). Thus, a job’s size can represent the number of tokens processed in parallel, while jobs with different sizes may still have almost the same service times. Moreover, empirical serving traces suggest that prompt lengths can follow an approximately decreasing distribution, particularly when chunked prefill is not used.

**Caching Policies Analysis and Development**

In addition, I am interested in designing and analyzing caching policies for modern LLM serving systems. Our <a href="https://arxiv.org/abs/2609.02027">recent work</a> develops a mean-field approximation for the hit ratio of the widely used Least Recently Used (LRU) policy. Our theoretically-motivated estimator achieves surprisingly low errors in real LLM serving experiments, particularly at large cache capacities, via tensor parallelism across multiple GPUs or NPUs. Several ongoing projects and research ideas building on this work are described below. If you are interested in any of the open directions on this page that are not yet ongoing projects, please feel free to contact Izzy or me, or my collaborator, <a href="mailto:ylyuad@connect.ust.hk">Yuan Lyu</a>, at HKUST.

<h3> [Ongoing] Mixtures of Multiple Workflows under LRU: </h3>

Our mean-field analysis shows that the eviction age of any tagged conversation converges to a deterministic characteristic time governed jointly by prompt-arrival dynamics and workload statistical structure. However, when a prefiller handles multiple workflows with substantially different workload characteristics and arrival dynamics, standard LRU assigns them essentially the same eviction age, as long as their next prompts do not arrive before eviction.  

Consider two workflows sharing a prefiller with a resulting characteristic eviction age of 120s. Suppose the turn interarrival times of the two workflows are exponential with means of 20 and 200 seconds, respectively. Do we really need to retain conversations from the first workflow for the full 120 seconds? Can we instead allocate cache capacity across workflows to deliberately create different characteristic eviction ages?

The answer is YES. We have developed a workflow-aware LRU policy that allocates cache capacity across workflows according to their distinct statistical characteristics. We have proved that this policy achieves a higher hit ratio than standard LRU, and we are currently evaluating its empirical performance. I am pursuing this project with Chutong Gao, Yuan Lyu, and <a href="https://www.linkedin.com/in/ziyuanwang1031/">Ziyuan Wang</a>.

<h3> [Actively Pursuing] Segmented LRU (SLRU)'s Mean-Field Performance and Hit Ratio Optimization:</h3>

SGLang now offers Segmented LRU (SLRU) as a cache-management option. Unlike standard LRU, SLRU partitions the KV cache in HBM into two segments: a protected (P) segment and a probationary (R) segment. Each segment maintains its own LRU ordering. A newly inserted KV block is placed at the most-recently-used (MRU) end of the R segment. Once the block is reused, it is promoted to the MRU end of the P segment. When a block is displaced from the P segment, it is demoted to the MRU end of the R segment, giving it another opportunity to be reused before it is eventually evicted from HBM.

SGLang does not impose a fixed capacity ratio between the P and R segments. Consequently, the protected segment may expand until it occupies the entire HBM cache. Although this can be desirable in practice, it introduces transience into the theoretical analysis. As a tractable first step, we  consider a constrained variant with a fixed capacity split, where the P-to-R ratio is α:(1−α). More broadly, the classical caching literature has studied related multistage policies, the LRU(m) family analyzed by <a href="https://www.sciencedirect.com/science/article/pii/S0166531617300688">Gast and Van Houdt</a>. Within our fixed-partition framework, we consider a k-hit SLRU(α) policy for LLM KV-cache management: a KV block is promoted to the protected segment only after receiving k hits while residing in HBM, with the protected and probationary segments occupying fractions α and 1−α of the total HBM cache capacity, respectively.

Can we extend our mean-field analysis to show that the eviction ages of the two segments converge to deterministic values? My preliminary numerical experiments—not yet LLM serving experiments—suggest that such convergence indeed occurs. The analytical proof introduces an additional challenge. In our analysis of standard LRU, the arrival process is exogenous. Under SLRU, however, the effective arrival process to each segment depends on both exogenous block requests and endogenous promotions or demotions from the other segment. The two segments therefore form a coupled stochastic system that requires a more sophisticated analysis.

An alternative performance analysis is to follow the approach of Gast and Van Houdt: assume that the two eviction ages are deterministic and then use Little’s law and the capacity constraints to solve for their values, thereby approximating the hit ratio of SLRU. I have confirmed the feasibility of this approach for our model. Specifically, we can tag the group of KV blocks generated at turn-j and assign it a state. By characterizing its state transitions and expected sojourn time in each state, we can calculate how long, in expectation, the block group resides in each segment over its lifetime, up to its eventual eviction after the conversation terminates. These expected residence times can then be used to formulate the capacity equations for the two segments. One remaining theoretical question is whether the resulting fixed-point equations always admit a unique pair of eviction ages. I have not yet established such a uniqueness result, and I warmly welcome researchers who are interested in working with me on this problem.

<h3>[Actively Pursuing] Queueing Networks for Hierarchical KV-Cache Storage </h3>

As multi-turn conversations and agentic workflows become increasingly common in LLM applications, the limited HBM capacity of GPUs and NPUs is often insufficient to support efficient KV-cache reuse under high load. A natural solution is to introduce lower-capacity-cost storage tiers. Both vLLM and SGLang support mechanisms that use CPU DRAM as a lower tier beneath HBM, while <a href="https://arxiv.org/abs/2407.00079">Mooncake</a> goes further by incorporating distributed CPU DRAM and SSD resources to support KV-cache reuse at a much larger scale.

In fact, developing a queueing-network model for such hierarchical storage systems was my original motivation for hit-ratio analysis. A meaningful queueing model, however, requires an accurate characterization of cache hits at each tier. Because this foundational problem had not been focused in the operations-research community, we decided to begin there. Building on our hit-ratio results, we can distinguish among the HBM, CPU, and SSD hit ratios and model the different paths that KV blocks take through the system. The proportions of requests following these paths, together with their corresponding service demands, can then be used to analyze time-to-the-first-token (TTFT). An HBM hit requires only a cache lookup and an update to the LRU ordering. Retrieving KV blocks from CPU DRAM or SSD additionally incurs data-transfer latency and the overhead of maintaining replacement states across multiple storage tiers. A complete miss is even more expensive because the missing KV states must be recomputed through prefilling. Quantifying these service times requires careful measurements from real LLM serving systems.  

This queueing-network perspective was inspired by <a href="https://link.springer.com/article/10.1007/s11134-026-09986-1">recent work</a> by Prof. Mor Harchol-Balter and her collaborators, which shows that increasing the cache hit ratio can sometimes reduce system throughput. Although I do not currently expect the same paradox to arise in LLM serving, a hierarchical KV-cache system creates many interesting opportunities for optimizing routing, cache placement, resource allocation, and load balancing across storage and computation resources. If you are interested in developing this queueing model with me, please feel free to get in touch!

Teaching & Teaching Assistantship
------
**Northwestern University, IL, USA**

*Teaching Assistant, Department of Industrial Engineering and Management Sciences*

<h4>IEMS 315 Stochastic Models (Undergrad. Lv), Fall 2026 </h4>
<h4>IEMS 304 Statistical Learning for Data Analysis (Undergrad. Lv), Spring 2026 [<a href="https://github.com/Heyuan-Yao/Heyuan-Yao.github.io/blob/master/_pages/SP26IEMS304Sec1.pdf">Session 1 Evaluation</a>] [<a href="https://github.com/Heyuan-Yao/Heyuan-Yao.github.io/blob/master/_pages/SP26IEMS304Sec2.pdf">Session 2 Evaluation</a>]</h4>
<h4>IEMS 315 Stochastic Models (Undergrad. Lv), Fall 2025 [<a href="https://github.com/Heyuan-Yao/Heyuan-Yao.github.io/blob/master/_pages/Individual%20Report%20for%20Heyuan%20Yao%20(IEMS_315-0_01%20%20Stochastic%20Models)_ae083803-227e-42f9-9080-a2033abbb70fen-US.pdf">Evaluation</a>] [Outstanding Teaching Assistant Award Honorable Mention in BSIE Program in AY 25/26]</h4>

**Columbia University in the City of New York, NY, USA**

*Teaching Assistant, Department of Mathematics*

<h4>MATH UN2015, Linear Algebra and Probability, (Undergrad. Lv), Spring 2024 [<a href="https://github.com/Heyuan-Yao/Heyuan-Yao.github.io/blob/master/_pages/MATHUN2015LinearAlgebraandProbabilitySpring2024-MATHUN2015_001_2024_1-LinearAlgebraandProbabilityMATHW2015_001_2024_1_183506_HeyuanYao.pdf">Evaluation</a>]</h4>
<h4>MATH GU4032, Fourier Analysis (Grad. Lv), Fall 2023 [<a href="https://github.com/Heyuan-Yao/Heyuan-Yao.github.io/blob/master/_pages/MATHGU4032_001_2023_3-FOURIERANALYSISMATHW4032_001_2023_3_170719_HeyuanYao.pdf">Evaluation</a>]</h4>
<h4>MATH UN2500, Analysis and Optimization (Undergrad. Lv), Spring 2023 [<a href="https://github.com/Heyuan-Yao/Heyuan-Yao.github.io/blob/master/_pages/MATHUN2500_002_2023_1-ANALYSISANDOPTIMIZATIONMATHV2500_002_2023_1_162640_HeyuanYao.pdf">Evaluation</a>]</h4>
<h4>MATH UN2500, Analysis and Optimization (Undergrad. Lv), Fall 2022 [<a href="https://github.com/Heyuan-Yao/Heyuan-Yao.github.io/blob/master/_pages/MATHUN2500_002_2022_3-ANALYSISANDOPTIMIZATIONMATHV2500_002_2022_3_150375_HeyuanYao.pdf">Evaluation</a>]</h4>

*Teaching Assistant (Grader), Department of Statistics*

<h4>STAT GU4207, Elementary Stochastic Processes (Grad. Lv), Spring 2024</h4>
<h4>STAT GU4203, Probability Theory (Grad. Lv), Fall 2023</h4>
<h4>STAT UN2103, Applied Linear Regression Analysis (Undergrad. Lv), Spring 2023</h4>
<h4>STAT UN1101, Introduction to Statistics (Undergrad. Lv), Fall 2022</h4>

**City University of Hong Kong, Hong Kong SAR Sep. 2020 – May 2021**

*PALSI Leader (Peer-Assisted Learning scheme using Supplemental Instruction)*

<h4>MA1201, Calculus and Basic Linear Algebra II, (Undergraduate level) Spring 2021</h4>
<h4>MA1200, Calculus and Basic Linear Algebra I, (Undergraduate level) Fall 2020</h4>


