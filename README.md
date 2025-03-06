# ucb-mlai-capstone
UC Berkeley ML-AI Capstone project

## Problem:

Looking to improve upon the AI tools used as software development aids that are currently available in the industry such as Copilot and ChatGPT.  The areas of improvement would revolve around being able to go from use cases to a more iterative process that minimizes the amount of software written by a software engineer.  The software in question would be the product of what is normally used in a implementing and deploying a software application as well as the work required to unit and regression test said application.

 

## Data:

The type of data used to implement this process would be what is generally found in Large Language Models (LLMs) like GPT-4 and LLaMA.

 

## Techniques:

I have just started looking at the problem with regards to what other people have done, so with regards to what techniques to use, that is still unclear.  I would think something along the lines of doing some form of Natural Language Processing incombination with techniques used in a Generative AI algorithm.  To start I would be looking at the innter workings of Retrieval Augmented Generation (RAG) and Generative Adversarial Networks (GAN).

Topics to investigate:
- Prompt Engineering
- Variational Autoencoders (VAEs)
- Generative Adversarial Networks (GANs)
- Transformers
- Retrieval Augmented Generation (RAG)
- LLM Architecture, Fine-Tuning and Benchmarking
- Attention Mechanism
- Langchain for Workflow Design
- GenAI Application Development
- Stable Diffusion
- Generative AI Governance.  Key points about generative AI governance:
  - Focus on responsible use: It aims to mitigate potential harms associated with generative AI, such as the creation of misinformation, biased content, or deepfakes.
  - Ethical considerations: Governance frameworks address ethical issues like fairness, accountability, and privacy related to generative AI applications.
  - Data management: Proper data governance practices are crucial to ensure the quality and integrity of the data used to train generative AI models.
  - Transparency and explainability: Governance should promote transparency in how generative AI systems function, allowing users to understand how outputs are generated.
  - Monitoring and oversight: Continuous monitoring of generative AI systems is necessary to detect and address potential issues as they arise. 

## Tools and Technologies to investigate:
- LangChain
- Streamlit
- Gradio
- Chroma
- Hugging Faces
- Dall-E2
- Bard


### Vector databases:
- pine cone: https://www.pinecone.io/
- weaviate: https://weaviate.io/
- chroma: https://www.trychroma.com/  (good for beginners)
- postgres with plugin for vector database.
- pgvector: https://github.com/pgvector/pgvector


### Retrieval step:
- embedding using transformers (not)

#### Transformers:
- Python encoding vectorizing: https://sbert.net/docs/sentence_transformer/pretrained_models.html
- Google: BARD which is now Gemini

Basic RAG workflows: !["rag-workflow-per-savio-saldanha.png"](<images/rag-workflow-per-savio-saldanha.png>)


## Application Definition:

### 1. AI-Driven Software Design & Architecture
- Current Challenges:
  - A key area of improvement is ensuring AI tools can assist more deeply in the design phase—shaping software architecture that is scalable and meets the use cases. For instance, tools like Copilot can help with writing boilerplate code, but improving their capacity to understand software design patterns, architecture decisions, and applying them in iterative steps is needed.
- Potential Improvements:
  - Implement AI-driven support for architectural diagrams and models (e.g., creating UMLs, entity-relationship diagrams).
  - Use AI to suggest improvements and refactor designs based on patterns it learned from previous successful projects.
- Resources:
  - AI for Software Design: Research paper on how AI can assist in design phases.
  - Machine Learning for Software Design (Book): Talks about applying ML to software design tasks.
### 2. Automated Code Generation with Contextual Iterations
- Current Challenges:
  - Tools like Copilot generate code based on the current context, but they still fall short when it comes to adapting to iterative improvements. They don’t easily handle the complexity of evolving software or understand the full context of the product being developed.
- Potential Improvements:
  - Contextual Code Generation: Focus on creating AI tools that can track changes over multiple iterations, learning from past changes and offering better suggestions over time. This includes generating better deployment scripts, unit tests, and handling regression testing.
  - Integration with Version Control: AI tools can be better integrated into version control systems (e.g., GitHub) to improve continuous development pipelines and make smart suggestions based on the project’s history.
- Resources:
  - DeepCode AI: AI-powered code review tool that provides suggestions based on the context of the software.
  - Code Generation and Refactoring with AI (Article): How AI can be used for automated code generation in an iterative context.
### 3. AI-Powered Testing Frameworks
- Current Challenges:
  - Unit/regression testing tools (like Jest, JUnit) are often manually written and maintained by developers. AI could significantly reduce the amount of effort in creating and maintaining these tests.
- Potential Improvements:
  - Test Generation: AI tools can generate unit tests based on the code and the project’s specifications. This could include a stronger understanding of edge cases and validating the most common failure modes.
  - Test Coverage Optimization: AI could analyze test coverage gaps and suggest tests that are likely to improve the overall coverage.
  - Regression Test Management: AI could learn from previous deployments and iterations to prioritize which tests are more important for specific updates, helping to avoid running full test suites.
- Resources:
  - AI-Driven Test Generation: Research paper on AI approaches for test generation.
  - Machine Learning in Software Testing (Book): Covers how machine learning and AI are used to optimize testing efforts.
### 4. Automated Deployment Pipelines with AI Optimization
- Current Challenges: Deployment scripts and CI/CD pipelines are often manually written, and there is potential to use AI for automation and optimization of these processes.
- Potential Improvements:
  - Automated Deployment Code Generation: AI could create optimized deployment scripts (e.g., Kubernetes, Docker configurations) based on the app's context and environment.
  - Optimizing CI/CD Pipelines: AI could analyze the pipeline’s history and suggest optimizations (e.g., order of steps, skipping unnecessary steps).
  - Automatic Rollbacks and Monitoring: Tools could help automate error detection and rollbacks based on real-time monitoring of app performance and failures.
- Resources:
  - AI and Automation in DevOps (Article): How AI can assist in automating DevOps processes.
  - AutoML and CI/CD (Article): How AI techniques can be integrated into CI/CD pipelines.
### 5. Human-AI Collaboration and Feedback Loops
- Current Challenges:
  - Current AI tools, such as Copilot and ChatGPT, are great at offering suggestions but require a lot of manual intervention and human oversight. The iterative feedback loop between human developers and AI tools can be optimized.
- Potential Improvements:
  - Self-Improving AI Models: As developers interact with AI tools, the AI could learn from corrections, decisions, and preferences to tailor future suggestions more closely to the project’s needs.
  - Collaborative IDEs: Use AI assistants that work within IDEs (e.g., VSCode, IntelliJ) that continuously learn from the developer’s corrections and enhance the experience over time.
- Resources:
  - Collaborative AI Programming (Research Paper): Studies how AI can help collaborate with developers more effectively.
  - Human-in-the-Loop AI: Book on how to design AI systems with iterative feedback from humans.
### 6. End-to-End AI Development Assistants
- Current Challenges:
  - While AI tools like Copilot assist with writing code, they are not yet capable of managing the full software lifecycle (from requirement gathering, design, coding, testing, deployment, to maintenance).
- Potential Improvements:
  - AI-Assisted Lifecycle Management: Create more integrated AI tools that can assist in all phases, from requirement analysis (using natural language understanding) to testing and deployment automation.
  - AI-Driven Documentation: AI could automatically generate and maintain documentation throughout the development lifecycle, reducing manual effort.
- Resources:
  - End-to-End Machine Learning Systems: Paper on how AI tools can cover the entire ML development lifecycle (some principles can apply to software engineering).
  - AI-Driven Full DevOps Lifecycle: How AI is shaping end-to-end management in software development.

