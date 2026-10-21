# College Cost Calculator by College Azimuth

Can you afford the college you're considering? This plugin lets Claude answer that with real numbers. It uses College Azimuth's Financial GPS and the federal student loan rules in force since July 1, 2026.

For a school and a field of study, it works out:
- what a student would owe when repayment starts;
- the payment that clears that debt in ten years;
- how much of their pay above basic living costs the payment takes.

The share comes with a plain label: Excellent, Good, Concerning or High risk. Parents get the same check for Parent PLUS on a stricter scale (Safe, Caution, High pressure), plus what the standard plan would actually bill, and at what ages.

The figures come from College Scorecard data served by College Azimuth, and from the current federal rates. College Azimuth's site runs the same rules on its [Financial GPS tools](https://collegeazimuth.com/financial-gps/).

## What's in it

- **A connector** to College Azimuth's server at `https://mcp.collegeazimuth.com/mcp`. It has eight read-only tools:

  | Tool | What it does |
  |---|---|
  | `find_school` | Finds a school |
  | `get_school` | A school's costs, debt, earnings and fields |
  | `student_check` | The student check |
  | `parent_check` | The Parent PLUS check |
  | `family_check` | The family check: paying for school, then who repays what |
  | `compare_schools` | Compares two to four schools on the same inputs |
  | `review_award_letter` | Totals an award letter and flags loans dressed as aid |
  | `get_loan_rules` | The dated federal loan rules |

- **A skill, `financial-gps`.** It teaches Claude:
  - when to use each tool;
  - the July 2026 loan rules;
  - how to read an award letter;
  - how to present results without overstating them.

## Use it

Ask in your own words. For example:

- "Is biology at UIC affordable if I borrow about $4,000 a year?"
- "My parents are thinking about Parent PLUS for Duke, around $7,000 a year. They make $120,000 and my dad is 55."
- "Here's my award letter from Boston University. What does it really cost?" (then paste the lines)
- "Compare UIC, Duke and Auburn for biology if I borrow $5,000 a year."
- "What's RAP, and how is it different from IBR?"
- "Can my mom put a new Parent PLUS loan on an income-driven plan?"

On claude.ai and in Cowork, connect the College Azimuth connector from the plugin's Connectors tab after adding the plugin. In Claude Code, install it with:

```
/plugin install college-azimuth --marketplace DanielAM923/college-azimuth-plugin
```

On Claude Code versions before 2.1.275, add the marketplace first, then install:

```
/plugin marketplace add DanielAM923/college-azimuth-plugin
/plugin install college-azimuth@college-azimuth
```

The connector connects when the plugin loads. No account or sign-in is needed.

## What data it sends, and where

- When Claude calls a tool, the tool's inputs go to College Azimuth's server at `mcp.collegeazimuth.com`. Inputs include a school, a field, borrowing amounts, household income, an age, or award-letter lines you share.
- The server reads College Azimuth's own data API to get the school's figures, computes the results, and returns them to Claude.
- Nothing you send is stored. The server doesn't log tool inputs such as incomes, ages or amounts.
- Its logs keep only the tool name, the school, whether the call worked and how long it took, for 30 days.
- The plugin itself runs no code on your computer and reads none of your files or conversations.

## Privacy

See [collegeazimuth.com/privacy](https://collegeazimuth.com/privacy/#ai-assistants) for the full privacy policy, including its section on College Azimuth in AI assistants.

## Who it's for

It's intended for adults (18+): students and parents using Claude to plan for college. It's educational analysis, not financial, tax or legal advice, and not a prediction of any one person's outcome.

## What it doesn't do yet

- **Repayment-plan payments:** it explains RAP and the new standard plan. The only plan bill it calculates is the standard plan's for Parent PLUS, in the parent and family checks. It doesn't estimate RAP or income-driven payments, or a standard-plan bill for a student's own loans. Choosing a repayment plan is a different question from whether a school is worth it.
- **Local living costs:** the basic-expense allowance is a national figure.
- **Salaries by city, career paths and rankings.**
- **Graduate and professional programs.**

## Support

Questions, problems or security reports: daniel@collegeazimuth.com. Setup help and troubleshooting: [collegeazimuth.com/help-claude](https://collegeazimuth.com/help-claude/).

## License

MIT. See [LICENSE](LICENSE).
