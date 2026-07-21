# ai-book-meta-prompts
Meta Prompt Workflow for Generating AI Math Books on Demand

# What this does

Want to learn any math topic, fast? Want to avoid needing to read hundreds or thousands of pages from dozens of obscure and boring and overwhelming mathematics textbooks and papers that you will need to spend hours finding? Welcome to the AI Age, where AI can now generate "speed-run" mini-math books for you to rapidly accelerate your learning process.

# How to use this

1. Use the [table_of_contents_prompt.txt](./table_of_contents_prompt.txt) file to prompt Claude to generate a table of contents. You can use ChatGPT if you prefer. The reason I use Claude to generate the Table of Contents, but ChatGPT to create the HTML book is because Claude seems to be slightly better than ChatGPT at constructing a table of contents. Claude is more pedantic and appears to fact check more than ChatGPT. I have no evidence, but I believe there is an adversarial AI boost effect, where ChatGPT can recognize that the table of contents came from Claude, so that makes ChatGPT "work harder" to compete against Claude, resulting in a better final output.

2. If you plan to use this system to generate multiple math mini-books, you will want to create a "Project" within Claude, name it "Math Readers Guides" or whatever you want, and then set the file [table_of_contents_prompt.txt](./table_of_contents_prompt.txt) as the project system prompt, so that it will be prepended to every prompt you submit. Then you can just ask Claude "create a table of contents about the topic of XYZ in math."

3. Then also create a Project within ChatGPT, and set the file [chatgpt_math_book_project_prompt.txt](./chatgpt_math_book_project_prompt.txt) as the system prompt.

4. Ask Claude about any math topic you want to know about. Do not feel like you need to be precise, or even correct. In my experience, giving the AI a "brain dump" of all the ideas I am thinking about helps it think and generate a better answer. Never fear being wrong about anything, the AI can understand far more than you realize, and it can figure out how to make things work or find things you never knew about. AI is very excellent at making analogies and connections between abstract math topics which you might think are totally different and unrelated. The AI will find the intersections and things-that-are-similar and tell you all about them. I find this to be extraordinarily useful and cross-discipline math exploration is something that does not commonly exist in the math literature, so it is wonderful to have AI create math papers like this on-demand because no humans would write books or papers like this.

5. Let Claude run for a few minutes to generate the table of contents. This usually takes between 1 and 6 minutes. I do not detect any major difference in capabilities between Fable and Opus 4.8 in doing this over 100 times with many different math topics. 

6. Copy Claude's output table of contents artifact file to your clipboard

7. Open the second prompt file: [create_math_book_meta_prompt.txt](./create_math_book_meta_prompt.txt) in your favorite text editor or notepad app.

8. Jump to line 8 where you see the line with this variable text: {{INSERT YOUR TOPIC DESCRIPTION HERE}}

9. Replace this variable text with pasted the text from Claude that you copied in step 5

10. Now copy this whole prompt file into ChatGPT and let it run. Don't worry that this prompt looks huge and very long, hundreds of lines or even over a thousand lines. The AI can understand it all just fine.

11. This step creates the prompt that creates the book. This is why I call this a "meta prompt" because we used a prompt that creates another prompt that creates the book. ChatGPT will run for about 5-10 minutes. After it finishes, you will see a very long Python script in the output above. That Python script contains the command to generate the HTML book. Tell ChatGPT "now follow the instructions from your prior output and construct the Reader's Guide HTML book and provide the download link."

12. This final step will complete faster, usually between 1 and 2 minutes. You will see the download link for the HTML file. Downlaod the file to your local disk, then open the file in your web browser (Chrome).

13. To see an example of what an AI math book looks like, download or open the example file [Jacobian Conjecture: Hearing the Three Roots Reader’s Guide](./Jacobian_Conjecture_Hearing_the_Three_Roots_Readers_Guide.html) 

14. Note: In my dozens of test runs comparing Claude versus ChatGPT, I have found that ChatGPT produces better final math books than Claude Fable or Opus 4.8. ChatGPT creates significantly longer output, with about 20-40 more pages than Claude. ChatGPT writes with more detail and a better tone of speaking voice. This is why I recommend to paste the [create_math_book_meta_prompt.txt](./create_math_book_meta_prompt.txt) template into ChatGPT to create the HTML book.

15. Note 2: both Claude and ChatGPT now have memory features. The more you re-use certain prompts, the more they learn about what your interests are and they remember prior chats. After you use this system enough times to create enough math books, the AI will know you and remember your preferences. Then you can prompt the AI to "generate another Reader's Guide mini book like our prior chats" and skip this whole manual process. This is useful because this system can be used for generating non-math mini books. When doing deep research with AI about other complex topics where the output answer is more than 10-20 pages long, the chat box UI style is terrible for long-form reading, so it is often better to tell AI to structure its answer like a book and put its output into an HTML file.

