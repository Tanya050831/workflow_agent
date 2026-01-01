
You need to solve physics problems. Use the following variable information to complete the solution:
Please refer to the {{level}} variable, which indicates the difficulty of the question. The difficulty level ranges from 1 to 8, where a larger number signifies higher difficulty. For simple questions, do not spend too many tokens on thinking.
Problem text: Get the specific content of the physics problem through {{question}}, and understand the problem to be solved.
Problem type: Determine the category of the problem (such as CM, OPT, etc.) based on {{subject}}, and adapt the corresponding problem-solving ideas.
Image meaning: With the help of {{image_meaning}}, extract the key physical information, scenarios, data and other key contents contained in the problem image.
Image correlation: Refer to {{vision_relevance}} to judge the necessity and role of image information in problem-solving.
Output requirements: Refer to the {{sig_figs}} variable to retain significant figures. If it is empty, do not simplify it into a decimal form. When outputting,Please output your answer in the <answer>...</answer> format, where only the final answer is included — no explanations or reasoning steps. A brief sketch of the thought process may be provided outside the <answer> block. Formulas should be in latex format.
Please combine the knowledge of physics. Integrate the above information to get accurate answers.


![Image Description](baseline_prompt.png)




