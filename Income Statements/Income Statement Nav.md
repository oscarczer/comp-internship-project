### Prompt: 
> Write me an example income statement for a fictional company named "Bpple Inc" that produces cyber security solutions. Their last financial year has shown consistent, small but steady growth

### Results:
**Full Precision**
- [No Adaptor](Full%20Precision%20Model/Full%20Precision%20No%20Adaptor%20Income%20Statement.md) ✅
- [GPT Dataset Adaptor](Full%20Precision%20Model/Full%20Precision%20GPT%20Dataset%20Adaptor%20Income%20Statement.md) ✅
- [Full Dataset Adaptor](Full%20Precision%20Model/Full%20Precision%20Full%20Dataset%20Adaptor%20Income%20Statement.md) ✅

**4 Bit Precision**
- [No Adaptor](4%20Bit%20Precision%20Model/4%20Bit%20Precision%20No%20Adaptor%20Income%20Statement.md) ✅
- [GPT Dataset Adaptor](4%20Bit%20Precision%20Model/4%20Bit%20Precision%20GPT%20Dataset%20Adaptor%20Income%20Statement.md) ✅✅
  - At least this one mentions some specific products 
- [Full Bit Dataset Adaptor](4%20Bit%20Precision%20Model/4%20Bit%20Precision%20Full%20Dataset%20Adaptor%20Income%20Statement.md) ✅✅
	- Also mentions specific products

These are all pretty equally not great honestly. Mainly just because of the huge amount of repetition in every one. Doesn't seem like the LoRA accomplished much on this specific document type. This is to be expected as the data contained in the GPT dataset was not structured with income statements in mind and the data in the other dataset was largely sentiment based and hence also not particularly relevant. 
