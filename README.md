### Introduction
It is worth noting that the following navigation system has been designed to be used within Obsidian (a free markdown note taking software). It is possible to view the results without this as everything is also in folders but if it is possible I would highly recommend browsing in Obsidian as it makes it substantially easier. For anyone who may be looking at this other than Daniel or myself I'm happy to respond to any questions at oscar.czernuszyn@penten.com

For information on how this project worked and what was actually performed, please see the [Further Reading Page](Further%20Reading.md) 

### System Input

The following input was provided in front of each of the document type specific prompts to try make it more specific for a financial document context

> You are a financial writer that writes about fictional companies for educational purposes. 
> Provide your own figures regarding company performance as long as they are in line with overall performance to give an accurate example of what a financial document should look like. 
> Also provide fictional dates to make the report look realistic. 
> Start your response from the actual report itself, do not introduce the report beforehand. 
> Be sure to provide a realistic fictional name anytime that someone's name is mentioned in the report, including when signing off. 

### Reviews:
❎ - Actively pretty bad. One look and you can tell it's fake  
✅ - Not fantastic but if just skimming may pass as real   
✅✅ - Not perfect but usable for general purposes   
✅✅✅ - Perfect / near perfect   

- [Financial Reports](Financial%20Reports/Financial%20Report%20Nav.md)
- [Budgets](Budgets/Budget%20Nav.md)
- [Income Statements](Income%20Statements/Income%20Statement%20Nav.md)
- [Announcements](Announcements/Announcement%20Nav.md)

### General Comments:
It seems like the financial reports and announcements performed the best. Whether this is to do with the structure of the data used for the LoRA training or simply because those prompts may have been clearer/more specific I am unsure of. It is clear that just feeding in sentiment data doesn't always help though as Llama seems to already do a pretty good job with this and adding more of it seems to have just led to minor overfitting in some cases. However, introducing the model to original, structurally focused data did help quite a bit in some cases with at least making the model LOOK more professional/realistic even if it didn't necessarily read that way. It also made the outputs more conversational which is definitely as a result of the data used. This could be seen as a positive (e.g. for the reports and announcements) but could also been seen as a negative (e.g. for the other two). An important take away from this is that LoRA is not a one adaptor fits all solution and that whatever the model is fitted to will likely become the primary thing it is good at producing, even to the detriment of other documents that are similar in content but different in structure

