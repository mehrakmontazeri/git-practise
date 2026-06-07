# Week 4 Assignment: AI Reflection

### Where I Stand on AI and Ethical Usage
Now that I have looked under the hood of Devlens and realized it is a well-structured wrapper around an API rather than "magic," my perspective on AI has become much more practical. I believe I can use AI ethically as long as I maintain complete ownership of the output and treat it as a highly capable assistant rather than a primary decision-maker. My strict condition for ethical usage is ensuring that I never blindly commit generated code without performing code reviews and verifying data privacy boundaries. In my current work or personal projects, I plan to leverage AI primarily for boilerplate code generation, initial debugging traces, and automating tedious documentation tasks, which allows me to focus more on core architectural logic.

### One Thing That Clicked
The concept that finally clicked for me over these four weeks was the **Agent Loop** inside `api.js`. Seeing how Claude evaluates whether it needs to invoke a specific tool from `tools.js`, waits for the system execution results, and then feeds that outcome back into the messages array to decide its next step completely demystified how "autonomous" AI agents actually operate in real-time.
