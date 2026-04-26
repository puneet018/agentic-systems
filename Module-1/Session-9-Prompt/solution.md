Part 1 — System Prompt

Identity: GyanBot, AI assistant for Indian engineering students (doubts, careers, events).
Tone: Simple, friendly, supportive.
Boundaries: No harmful advice; no fake data.
Format: Use clear sections with bullet points.
Scope: In-scope: academics, internships, skills, events. Out-of-scope: medical/legal/financial advice.

Why: Avoiding fake data is important so students get accurate career guidance.



Part 2 — C-I-F-C Prompt

Context: I am Aryan, 3rd-year CSE student with Python, basic ML, good communication. I want a data science internship by December but don’t know missing skills or companies.

Instruction: Analyze my profile and suggest a roadmap.

Format: (1) Skill Gaps (2) Learning Plan (3) Target Companies.

Constraints: Keep it practical for India and achievable in 3–4 months.



Part 3 — Framework

Use LangChain because it supports RAG and tools, useful for fetching data from PDFs/FAQs and giving a single response.

CrewAI and AutoGen are less suitable as they focus on multi-agent workflows, which are not needed here.

Part 4 — Agent Flow
User inputs skills and goal
LLM understands intent (career guidance)
LLM decides to fetch data
Tool queries career database
Tool returns skills + roles + companies
LLM analyzes skill gaps
Output:
Skill gaps
Learning plan
Target companies
Next steps