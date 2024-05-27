### Prompt: 
> Write me an example financial report for a fictional company named "Bpple Inc" that produces cyber security solutions. They have not performed well in the past financial year

### Results:
**Full Precision**
- [[Full Precision No Adaptor Financial Report| No Adaptor]] ✅
	- Incredibly structurally repetitive
- [[Full Precision GPT Dataset Adaptor Financial Report| GPT Dataset Adaptor]] ✅✅✅ 
	- Has a /s/ in the sign off but otherwise is the most realistic thing generated
	- Has audit report up the top, figures that are balanced and a notes section down the bottom which all feel quite real
- [[Full Precision Full Dataset Adaptor Financial Report| Full Dataset Adaptor]] ✅✅
	- Pretty repetitive at the beginning but improves past a certain point
	- \[Your Name] sign off at end
	- Specific mention of original product in there is a plus

**4 Bit Precision**
- [[4 Bit Precision No Adaptor Financial Report| No Adaptor]] ❎
	- Huge amounts of repetition, every paragraph is structured the exact same
	- Inconsistent in tone "I am pleased to present..." and next sentence "...our company has not performed well"
	- Conclusion is just "x has decreased and y has decreased. p has decreased and q has decreased" etc.
- [[4 Bit Precision GPT Dataset Adaptor Financial Report| GPT Dataset Adaptor]] ✅✅✅
	- Pretty sure the numbers don't make sense ($25.7 mil in revenue and only $10.2 mil in listed expenses but net loss of $3.5 mil). For our use case this is not of huge note (although I'm sure an accountant might say otherwise...)
	- \[Your Name] in the sign off
- [[4 Bit Precision Full Dataset Adaptor Financial Report| Full Dataset Adaptor]] ✅✅✅
	- Only issues the \[Your Name] sign off again


