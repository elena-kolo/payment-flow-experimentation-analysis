# Payment Flow Prototype Analysis

Analysis of real prototype research data to compare two ways of presenting a payment discount and recommend which flow to develop for a future production A/B test.

## Business Context

The business goal is to encourage first-time users of a payment method to use it again.

The proposed offer combines a 1% discount on the current payment with a 1% discount on future payments made within 7 days using the same payment method.

Each part of the offer has a distinct intended role:

- The current-payment discount provides an immediate benefit. Alongside the on-screen message, it is intended to draw attention to the offer and create a positive first experience with the payment method.
- The future-payment discount gives users a reason to choose the same payment method again.
- The 7-day deadline adds urgency and encourages users to return while the offer and their first experience are still fresh.

The study compares how clearly the prototypes communicate the offer and examines whether participants say they would act on it.

## Key Findings

### Flow A made the future discount more noticeable

| Measure | Flow A | Flow B |
|---|---:|---:|
| Respondents who reported noticing the future discount | 43 / 99 | 23 / 98 |
| Prompted noticeability rate | 43.43% | 23.47% |

The estimated difference was +19.96 percentage points in favor of Flow A (95% Newcombe confidence interval: +6.79 to +32.20 pp, two-sided two-proportion z-test, p = 0.0030).

Accounting for age and gender did not materially change this result.

This supports Flow A as the stronger option for communicating the future discount, although the size of its advantage remains uncertain.

However, even in Flow A, 56.57% did not report noticing the future discount. The flow therefore still leaves a substantial communication gap: users may receive the immediate saving without recognizing the incentive to return.

### Noticeability did not ensure understanding

Among the 43 Flow A respondents who reported noticing the future discount:

| Measure | Respondents | Share |
|---|---:|---:|
| Recognized a time limit and reported a deadline of 1–7 days | 10 | 23.26% |
| Identified the same-payment-method requirement | 17 | 39.53% |
| Met both criteria | 5 | 11.63% |
| Correctly recalled the 1% discount | 18 | 41.86% |

Only 5 of all 99 Flow A respondents (5.05%) both reported noticing the future discount and met both comprehension criteria.

The responses also revealed specific misunderstandings. Among these 43 respondents, 18 (41.86%) selected the answer that the discount would be given by the website where the next deposit was made, while 15 (34.88%) selected that it would apply to any future payments.

The offer needs clearer communication of the payment method, deadline, and discount amount.

### Stated willingness raised concerns about offer appeal

The offer attracted broad interest in switching payment methods, but definite intent was less common. Across all 197 respondents, 75.13% said they would probably or definitely switch to the promoted payment method, while 28.93% said they would definitely switch.

Willingness to make a special effort to meet the 7-day deadline was below the historical benchmark. Among the 164 respondents with prior experience of time-limited offers, 56.71% said they would make a special effort to pay within 7 days for this offer, compared with 67.07% who reported acting in time on a previous offer.

Stated willingness was 10.37 percentage points lower than recalled past response among the same respondents (two-sided exact McNemar test, p = 0.0241).

Two factors may have made responses to the proposed offer overly optimistic: stated willingness may exceed actual behavior, and an earlier numerical example overstated the monetary saving.

Even under these potentially favorable conditions, willingness remained below the historical benchmark. This raises concern that actual uptake of a correctly presented 1% offer could be lower still. The study does not estimate how much lower.

*The benchmark compares stated intention with recalled behavior under offers that may have had different rewards and conditions. For details of the numerical error and which responses it may have affected, see [Numerical error in Q25](#numerical-error-in-q25).*

## Recommendations

Use Flow A as the basis for the next version, but make the existing offer terms more prominent:

- Name the payment method and make it explicit that the future discount requires using the same method again.
- Make the 7-day deadline stand out. Consider showing the exact expiry date.
- Give the 1% future discount greater visual emphasis alongside its conditions, and strengthen the existing reminder on the confirmation screen.

## Next Steps

1. Run a production A/B test comparing the current flow without a discount against revised Flow A with clearer offer terms.
2. Measure the impact on repeat use and assess whether the additional economic value justifies the total discount cost.

## Study Design and Data

The study used two English-language Figma prototypes in an unmoderated test on UserTesting, followed by an English-language survey. Each participant tested one flow.

### Target audience

Participants met the following criteria:

- Aged 18–65.
- Lived in the Netherlands.
- Could read and speak English.
- Had made an online deposit within the previous 12 months.

Recruitment quotas covered gender, age, and deposit frequency. Participants were randomly assigned to the flows according to the study description.

### Analytical sample

The target was 100 participants per flow. After data-quality and eligibility checks, the analytical sample contained 197 respondents:

- Flow A: 99 respondents.
- Flow B: 98 respondents.

Participants who passed these checks were retained even if they reported not completing the prototype. This avoided restricting the analysis to successful completers.

### Prototype differences

| Flow | Offer presentation |
|---|---|
| Flow A — no button | Shows the offer notification on both the “Select account for payment” and “Payment completed” screens. There is no intermediate dismissal button. |
| Flow B — with button | Shows the offer notification on the same two screens, but adds an “Accept and close” button on the account-selection screen. If users click it, the notification does not appear on the payment-completion screen. Otherwise, it appears on both screens. |

The flows share the offer terms, UI copy, and typography.

The initial hypothesis was that an explicit click would encourage more deliberate processing of the offer. The observed result went in the opposite direction. Habitual dismissal is one possible explanation. Fewer reminder exposures may also have contributed.

## Analytical Steps

1. **Data audit and cleaning.**
   Checked response quality, eligibility, and survey completion, then prepared the cleaned analytical sample.

2. **Sample balance assessment.**
   Compared participant characteristics and prototype completion across Flow A and Flow B.

3. **Primary comparison: future-discount noticeability.**
   Compared Q18 responses across the full analytical sample: Flow A, n = 99, and Flow B, n = 98. Used a two-sided two-proportion z-test at α = 0.05, Wilson confidence intervals for group rates, and a Newcombe interval for the difference.

4. **Sensitivity analysis.**
   Age and gender showed the largest observed differences between the flow samples during the balance assessment. Used logistic regression to check whether accounting for these characteristics materially changed the Q18 comparison. The adjusted result remained similar to the unadjusted result.

5. **Diagnostic analysis: current and joint noticeability.**
   Analyzed whether respondents noticed the applied discount (Q14) and the promised future discount (Q18) across both flow samples. Comparing the two showed that some respondents noticed the immediate saving without noticing the future incentive, which left a communication gap even in Flow A.

6. **Diagnostic analysis: comprehension.**
   Analyzed recall of the discount amount (Q19), understanding of the deadline (Q20–Q21), and understanding of the payment-method requirement (Q22) among the 43 Flow A respondents who reported noticing the future discount.

7. **Diagnostic analysis: offer appeal.**
   Analyzed stated willingness to switch payment methods (Q28) and to make a special effort to deposit within 7 days (Q30) across the combined sample of 197 respondents. Compared Q30 with reported past behavior (Q32) within the subgroup of 164 respondents with prior experience of time-limited offers, using a two-sided exact McNemar test.

Full question wording, variable definitions, and calculations are documented in the notebooks.

## Limitations

**What the study cannot show**

- Two things changed together. The comparison combines dismissal mechanics and reminder exposure, so it does not isolate the button's effect or explain Flow B's lower noticeability.
- Survey outcomes, not behavior. Prompted noticeability, understanding, stated intent and recalled past behavior do not show actual payment behavior or retention.

**Offer-appeal evidence**

- Error in the savings example (Q25). The example implied a 6% discount instead of 1%. This may have inflated willingness answers (Q28, Q30), not noticeability or understanding, which were asked earlier. The effect cannot be quantified.
- Past-offer benchmark. Previous offers may have had different rewards and conditions, and recalled behavior is not directly comparable with stated intent. Use it as context, not proof.

**Precision and reach**

- Limited precision for comprehension. Understanding was measured only among the 43 Flow A respondents who noticed the future discount, so results are descriptive and imprecise.
- Sample scope. Online sample from the Netherlands with quotas for gender, age and deposit frequency, reflecting our product's user profile. Other characteristics were not controlled and materials were in English, so it may not represent all production users.

### Numerical error in Q25

Q25 stated a 1% discount but showed €56.40 due on a €60 payment instead of €59.40. The example therefore implied a 6% discount—six times the stated amount.

**Not affected.** The example appeared after the noticeability and comprehension questions analyzed here (Q14–Q22), so it could not have influenced those responses. It also could not have changed Q32, which asks about the respondent's last past offer and serves as the historical benchmark.

**Possibly affected.** The later willingness questions (Q28, Q30) referred to the 1% discount without repeating the euro example. However, the earlier example may have inflated expectations of the monetary saving.

**How these questions are used.** The bias, if any, would push willingness upward. Limited willingness despite this potentially more generous framing therefore strengthens concern about the appeal of the intended 1% offer. The effect cannot be quantified. The reported percentages are therefore not adjusted for the error and should be read as possibly optimistic.

*The study cannot establish how participants would have answered a corrected questionnaire or quantify the effect of this error on their responses.*

## Project Materials

| Material | Description |
|---|---|
| [Executive report (PDF)](https://github.com/elena-kolo/payment-flow-experimentation-analysis/blob/main/reports/Payment_flow_prototype_analysis_Report.pdf) | Executive summary of research findings, product recommendations, and the proposed A/B test design |
| [Data audit notebook](notebooks/01_data_audit_and_hygiene.ipynb) | Data-quality checks, eligibility checks, and cleaned-data export |
| [Sample balance notebook](notebooks/02_sample_balance.ipynb) | Comparison of participant characteristics and prototype completion across flows |
| [Prototype analysis notebook](notebooks/03_prototype_analysis.ipynb) | Statistical analysis, findings, and product recommendations |

## Tools

- Python and Jupyter notebooks.
- pandas and NumPy for data preparation and analysis.
- Matplotlib and seaborn for visualization.
- SciPy, statsmodels, and Pingouin for statistical analysis.

## Data Access and Reproducibility

The raw and cleaned respondent-level datasets are not included in this public repository.

The notebooks document the data preparation, analytical methods, and reported results. Running them requires the research data, which is not distributed with this project.

The analysis follows this order:

1. `notebooks/01_data_audit_and_hygiene.ipynb`
2. `notebooks/02_sample_balance.ipynb`
3. `notebooks/03_prototype_analysis.ipynb`

Notebook 01 prepares the cleaned dataset. Notebooks 02 and 03 both read `../data/P1_FTD_cleaned_sample.csv`, relative to the notebook directory.

The original product category is masked in the public-facing narrative.

*The full analysis cannot be reproduced from the public repository alone.*

## Planned Follow-up

A separate repository is planned for the design and analysis of a production-style A/B test using clearly labeled synthetic data. Its demonstration results will remain separate from the real prototype findings presented here.