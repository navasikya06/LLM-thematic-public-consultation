# LLM-assisted thematic analysis of public consultations

This repo has 3 main notebooks:
- Scraping submissions from the government website: https://consult.industry.gov.au/supporting-responsible-ai/submission/list
- Filtering for organization submissions and extracting the relevant text by regex
- Using gpt-4o mini to do inductive thematic analysis of the relevant text following Braun and Clarke's framework

All data, codes and themes generated are included in the "output" folder.

Full process:

![image](https://github.com/user-attachments/assets/ddfe39ec-0a0f-44b1-88a2-4ca8bacc257e)

LLM thematic analysis:
![image](https://github.com/user-attachments/assets/7733b540-d49c-4c86-a377-3971bf735335)

Method adopted from Mathis et al. (2024):
- Step 1: Extraction of relevant text
- Step 2: LLM generates all codes from documents, concatenates all codes. Prompt: “Identify all themes in the text, provide a name for each theme in no more than 5 words, a condensed description of the theme, and a quote from the interview that supports the theme.”
- Step 3: LLM generates three iterations of themes from codes. Prompt: “Determine how all the topics in the list of topics can be grouped together. Topics can be in more than one group. Provide a name and description for each group, followed by all the topics in the group.”
- Step 4. LLM evaluates themes for flaws. Prompt: “List the areas for refinement and faulty logic of each answer option. Let’s work this out in a step by step way to be sure we have all the errors:”
- Step 5. LLM resolves flaws and generates best list of themes. Prompt: “You are a resolver tasked with finding the answers that best determines how all the topics in the list of topics can be grouped together.
1) removing any redundant or duplicate answers.
2) improving the answers based on the analysis of flaws
3) printing the improved answer in full
Let’s work this one out in a step by step way:”.
