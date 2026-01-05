# CHAPTER 1 Process meeting notes and user interview transcripts

Read @meeting-notes-raw.md and append a clean summary section to the bottom of the file

Read @product-sync-notes.md and create a new file called product-sync-email.md formatted as an executive email summary

Analyze all files in @user-interviews and create a new file called user-research-insights.md with the top 3 pain points and supporting quotes

# CHAPTER 2 Communication styles

List files in @communication-styles/ folder

Read all three style template files and present them

Read research-findings.md and all three template files, then create three new output files

# CHAPTER 3 Planning mode

Read @feature-announcement.md and present the details

Plan a multi-channel launch campaign for this feature. Research our positioning and target customers, aks clarifying questions, then create a go-to-market plan with messaging strategy, email sequences, and success metrics.

Create the planned deliverables, 2 files in this folder, campaign-plan.md and timeline.md

Generate a UI mockup image using Nano Banana Pro showing:
- RemoFlow-style interface with a task board or project view
- 2-3 colored cursors with teammate names (like "Sarah", "Mike")
- Presence indicators showing who's online
- Clean, modern design aesthetic
- Save as launch-feature-mockup.png

# CHAPTER 4 Project rules

Write a product update announcing the new Workspace Sharing feature, work in 5-project-rules folder, save as product-update-baseline.md

Help me create .agent/rules/remoflow-terminology.md with our product terminology and style preferences
- Terminology section: "Workspace" not "Project", "Task" not "To-do", etc. 
- Personas section: Reference Sarah (Enterprise Admin), Mike (IC Engineer), Alex (Team Lead). 
- Writing style: Active voice, Oxford commas, no emojis, conversational but professional. 
- Output preferences: Use real names in examples, include specific use cases.

Write a product update announcing the new Workspace Sharing feature, work in 5-project-rules folder, save as product-update-baseline-with-rules.md

# CHAPTER 5 Write PRDs

Read @prd-templates folder and compare PRD template versions

Read @taskflow-company-context.md and @user-research/pain-points.md

Use the Socratic questioning framework to sharpen my thinking on this feature

Generate 3 draft PRDs

Read <the chosen PRD version>, read all files in @reviewers/ folder (@engineer.md, @executive.md, @user-researcher.md), create ai-chat-todo-prd-review.md consolidating feedback from all three perspectives
- Engineering Perspective: Technical feasibility, implementation complexity, infrastructure needs, potential issues, recommendations
- Executive Perspective: Business value, strategic fit, market differentiation, resource commitment, ROI concerns, recommendations
- User Research Perspective: User needs validation, usability concerns, accessibility, adoption risks, recommendations
- Common Themes: Identify patterns across all three perspectives
- Priority Feedback Items: Rank by importance

In ai-chat-todo-prd-review.md consider item x, recommend me some options to handle this feedback

Edit <the chosen PRD version (v1, v2, or v3)> to incorporate feedback decisions
- Update phasing approach based on engineering feedback choice
- Add monetization section based on executive feedback choice
- Add onboarding/UX section based on UX feedback choice
- Refine success metrics to reflect new approach
- Update timeline if needed

# CHAPTER 6 Analyze Data

Analyze and find where users are dropping off in the activation flow
- Read activation-funnel-q4.csv. 
- Count users at each funnel stage (signup, created_first_task=TRUE, completed_first_task=TRUE, invited_teammate=TRUE). 
- Calculate completion rates at each stage. Present results as a formatted table. 
- Identify the biggest drop-off point and calculate the drop-off percentage. 
- Explain what this means for TaskFlow's activation problem.

Analyze it to extract the top themes explaining why users drop off at task completion
- Read user-survey-responses.csv. Analyze the 'feature_request' field to identify top themes and count frequency of each. 
- Calculate percentages. 
- Also analyze 'confusion_during_onboarding' field to extract powerful user quotes (2-3 representative quotes). 
- Check if there are any patterns by company_size. 
- Present findings with theme counts/percentages and memorable quotes. 

Create activation-problem-analysis.md that synthesizes all the discovery work. Include sections for: 
(1) Problem Statement with the key drop-off percentage, 
(2) Quantitative Evidence from the funnel analysis, 
(3) Qualitative Evidence with survey themes and quotes, 
(4) Segmentation Insight about which user segments are most affected, 
(5) Proposed Solution describing the Guided Onboarding with sample project concept, 
(6) Expected Outcome explaining how this will help. Make it executive-ready and well-formatted.

Read impact-estimation-framework.md and explain the core formula and the three-scenario approach. 
- Then explain how to apply it to guided onboarding by walking through each component (Users Affected, Current Rate, Expected Lift, Value per Action). 
- Emphasize that the key is modeling three scenarios to show the range of outcomes.

Read taskflow-usage-data-q4.csv to get monthly_signups, baseline_activation_rate, avg_ltv_activated_user, and engineering_cost_per_month. 
- Use the impact estimation framework to create guided-onboarding-roi-scenarios.md with three complete scenarios (Pessimistic at 20th percentile, Realistic at 50th, Optimistic at 80th). 
- For each scenario, model different adoption rates (low/medium/high), different activation lifts (conservative/moderate/strong), calculate incremental activated users per month, monthly revenue impact, 3-year revenue, and ROI vs. the engineering investment (assume 4 months, 2 engineers). 
- Include a Key Assumptions section documenting all inputs. Make reasonable assumptions for adoption rates and lift percentages that follow a pessimistic/realistic/optimistic pattern.

Summarize the key takeaways: highlight the ROI for each scenario, note that even the pessimistic case shows positive ROI, mention the strategic value beyond just the numbers, and state the total engineering investment.

Read the first 5-10 rows of onboarding-experiment-results.csv and display them as a formatted table to show the data structure. Then explain what columns are in the dataset and what we'll be analyzing (primary metric first, then segments, then quality metrics).

Read onboarding-experiment-results.csv. 
- Count users in each cohort (control vs treatment). 
- For each cohort, count how many have completed_first_task=TRUE and calculate the activation rate. 
- Calculate the lift in percentage points. 
- Present results in a formatted table. 
- Note whether the result is statistically significant (you can assume significance if lift is >5pp with 4000 users per cohort). 
- Then react to the results: compare the actual activation rate to our 58% realistic projection and note whether this is underwhelming or meets expectations.

Read experiment data and segment by company_size (5-20, 21-99, 100+). 
- For each segment, calculate control vs treatment activation rates and lift in percentage points. 
- Present each segment clearly with counts, rates, and lift. 
- Note which segments show strong positive results, neutral results, or negative results. 
- Add dramatic commentary about what this segmentation reveals - especially if there's a big difference between small teams (our target market) and other segments. 
- Emphasize how easy this was with Antigravity vs Excel.

Filter the experiment data to only users where completed_first_task=TRUE (activated users only). 
- For this filtered group, calculate: 
    - (1) Week 1 retention = percentage with days_active_week_1 >= 3, for control vs treatment, 
    - (2) Average tasks_completed_week_1 for control vs treatment. 
- Present in a formatted table with the lift. React enthusiastically to the results - note that we activated MORE users AND they're BETTER quality. 
- Explain the implications for LTV and revenue projections. 
- Point out how Antigravity made this filtered analysis instant vs rebuilding analysis in traditional tools.

Analyze two leading indicators from the experiment data: 
(1) Template usage - calculate % of users where used_template=TRUE for control vs treatment, and 
(2) Invite rate - calculate % of users where invited_teammate=TRUE for control vs treatment. 
- For template usage, optionally check if template users completed more tasks. 
- Present both metrics with control vs treatment rates and the multiplier. 
- Explain why these are fantastic signals for long-term success (template usage = stickiness, invite rate = viral growth and retention).

Create onboarding-experiment-readout.md that synthesizes all the experiment analysis we just did. Include sections for: 
(1) Executive Summary with clear recommendation, 
(2) Topline Results with overall activation rates, 
(3) Segment Analysis showing results by company size, 
(4) Quality Metrics covering retention and engagement, 
(5) Leading Indicators covering template usage and invite rates, 
(6) Recommendation explaining the launch approach (which segments to target, monitoring plan, next steps), 
(7) Expected Impact with projected incremental users, revenue, and ROI. 
Make it executive-ready and well-formatted with clear data points from all the analyses we just performed.

# CHAPTER 7 Product Strategy

Explain the three components of @rumelt-strategy-kernel.md (Diagnosis, Guiding Policy, Coherent Actions) VAGY Read frameworks/rumelt-strategy-kernel.md and extract key concepts

Search the web for Notion, Linear, and Asana's AI features, pricing strategies, and target markets. Then create a competitive landscape comparison table. VAGY Web search for all three competitors and synthesize findings

Help me develop a strategy using @rumelt-strategy-kernel.md and challenge my choices using @devils-advocate-strategy.md VAGY Read methods/devils-advocate-strategy.md

Using @rumelt-strategy-kernel.md, create h1-2026-ai-product-strategy.md organizing my 5 strategic choices into Diagnosis, Guiding Policy, and Coherent Actions VAGY Create h1-2026-ai-product-strategy.md using Rumelt's Strategy Kernel framework based on user's choices

Using @presentation-best-practices.md and @h1-2026-ai-product-strategy.md, create strategy-review-slides.md with 12-15 slides using action titles VAGY Create strategy-review-slides.md with 12-15 slides using action title format based on user's actual strategy