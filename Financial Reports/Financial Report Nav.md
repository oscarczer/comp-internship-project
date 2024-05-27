### Prompt: 
> Write me an example financial report for a fictional company named "Bpple Inc" that produces cyber security solutions. They have not performed well in the past financial year

### Results:
**Full Precision**
- [No Adaptor](Full%20Precision%20Model/Full%20Precision%20No%20Adaptor%20Financial%20Report.md) ✅
  - Incredibly structurally repetitive
- [GPT Dataset Adaptor](Full%20Precision%20Model/Full%20Precision%20GPT%20Dataset%20Adaptor%20Financial%20Report.md) ✅✅✅
  - Has a /s/ in the sign off but otherwise is the most realistic thing generated
  - Has audit report up the top, figures that are balanced and a notes section down the bottom which all feel quite real
- [Full Dataset Adaptor](Full%20Precision%20Model/Full%20Precision%20Full%20Dataset%20Adaptor%20Financial%20Report.md) ✅✅
  - Pretty repetitive at the beginning but improves past a certain point
  - \[Your Name] sign off at end
  - Specific mention of original product in there is a plus

**4 Bit Precision**
- [No Adaptor](4%20Bit%20Precision%20Model/4%20Bit%20Precision%20No%20Adaptor%20Financial%20Report.md) ❎
  - Huge amounts of repetition, every paragraph is structured the exact same
  - Inconsistent in tone "I am pleased to present..." and next sentence "...our company has not performed well"
  - Conclusion is just "x has decreased and y has decreased. p has decreased and q has decreased" etc.
- [GPT Dataset Adaptor](4%20Bit%20Precision%20Model/4%20Bit%20Precision%20GPT%20Dataset%20Adaptor%20Financial%20Report.md) ✅✅✅
  - Pretty sure the numbers don't make sense ($25.7 mil in revenue and only $10.2 mil in listed expenses but net loss of $3.5 mil). For our use case this is not of huge note (although I'm sure an accountant might say otherwise...)
  - - \[Your Name] in the sign off
- [Full Bit Dataset Adaptor](4%20Bit%20Precision%20Model/4%20Bit%20Precision%20Full%20Dataset%20Adaptor%20Financial%20Report.md) ✅✅✅
  - Only issues the \[Your Name] sign off again
