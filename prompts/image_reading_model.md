##读图模型的提示词


Based on the following information, please analyze and provide a precise description of the image presented in the physics problem.
Image Theme: Using the variable {{subject}}, identify the physics topic depicted in the image.
Image Content: Use the variable {{image}} to access the physical image material associated with the problem.
Image Category: Using the variable {{img_category}}, identify the type of physics diagram to which the image belongs (e.g., circuit diagram, free-body diagram).
Relevance Information: When the variable {{vision_relevance}} is "essential," focus on the physical information conveyed by the image, as it is crucial for solving the problem.
Auxiliary Description: Use the variable {{caption}} and refer to the image's textual description to aid in comprehension.
From a physics standpoint, please provide a clear and professional description of the image. This should include the physical scenario it presents, the physical elements involved (such as circuit components, objects under force), and its connection to physical laws or principles (for instance, whether it illustrates a model for a specific theorem or law). The goal is to achieve a precise interpretation of the physical image.

![Image Reading Prompt Configuration](image_reading_prompt.png)



