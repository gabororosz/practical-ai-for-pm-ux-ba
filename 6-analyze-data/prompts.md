# MODULE 6 Analyze Data

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