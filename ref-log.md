# INFO 5940 
ref-log.md
# Reference Log

## What did you learn from implementing a multi-agent workflow?

By implementing a collaborative workflow between the Planner and Reviewer, I gained a clearer appreciation for how role specialization enhances complex task execution. The Planner generates creative itinerary drafts from vague user requests, while the Reviewer verifies each detail using real-time online searches. This division of labor reduces the risk of hallucinations or inconsistencies, ensuring outputs are both imaginative and accurate. Each agent excels in its domain: the Planner innovates freely, unconstrained by fact-checking, while the Reviewer focuses on feasibility and real-world applicability. This experience reaffirmed that effective multi-agent systems depend on well-defined roles and structured communication—aligning architecture with each AI’s strengths to improve output quality and reliability.

## Challenges faced and how you addressed them

The primary challenge involved ensuring the Reviewer Agent consistently used the internet search tool and produced uniformly formatted Delta Lists. Early versions suffered from unreliable tool execution and inconsistent output structure. To address minor issues like text adhesion, stricter formatting rules were introduced—each of which, however, introduced new complications. A balance was eventually struck between strict constraints and output quality, leading to a workable solution. 

A second major issue arose during the integration of the Tavily API, where environment variables failed to load due to an incorrect file extension (env.txt). Troubleshooting revealed that the python_dotenv library only recognizes files named .env by default. Renaming the file using the mv command and mading some changes in the devcontainer.json, I resolved the issue, allowing both Tavily and OpenAI API keys to be read properly. This process improved my understanding of configuration standards and how dependency libraries operate. 

Prompt design also underwent multiple iterations. Initial versions enforced overly rigid formatting, which limited the model’s flexibility

## Any creative ideas, variations, or design choices (e.g., persona roles, prompt design)

Our multi-agent architecture assigns distinct roles to the Planner and Reviewer, creating a productive "visionary–executor" dynamic. The Planner devises a high-level itinerary, which the Reviewer then refines for safety and practicality.

To ensure operational rigor, the Planner must conclude every itinerary with a “Logistics:” section—transforming abstract planning into actionable directives.

Instructions are further reinforced with both positive and negative examples (e.g., “Museum closed Tuesdays → Rescheduled to…”). This method not only tells the AI what to do, but teaches it how to think, resulting in more reliable and thoughtful outputs.

## Note any external tools or GenAI assistance used and why

ChatGPT/DeepSeek are used to architecture analysis for multi-agent systems and Streamlit interface debugging.

The Tavily API powers the internet_search functionality to provide real-time fact verification for the Reviewer Agent.

Python-dotenv is used for secure API key management and environment configuration handling.

This technology stack effectively addressed technical challenges, accelerated development velocity, and ensured code reliability. The integration of Tavily API proved particularly critical, serving as the foundational component for meeting real-time fact-checking requirements.



