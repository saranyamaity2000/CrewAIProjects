## Crew AI Project Steps :

- > make sure uv is installed in your machine
  > `brew install uv`
  >


- > install crewai
  > `uv tool install crewai `
  >


- > use crewai command to create a new **crew** project
  > `crewai create crew project-name`
  > to start with one have to choose a starter **LLM** but later we can change it.
  > note - you can skip providing KEY in this step.
  >
- > under **project_name/src/project_name/config**
  > we have to setup,
  > **our agents under agents.yaml** (for dynamic values uses {} template place holder)
  >
  > ```yaml
  > debater: # Sample Agent
  >     role: >
  >         A compelling debater
  >     goal: >
  >         Present a clear argument either in favor of or against the motion. The motion is: {motion}
  >     backstory: >
  >         You're an experienced debator with a knack for giving concise but convincing arguments.
  >         The motion is: {motion}
  >     llm: openai/gpt-4o-mini
  > ```
  >
  > **our tasks under tasks.yaml** (for dynamic values uses {} template placeholder)
  >
  > ```yaml
  > propose: # sample task
  >     description: >
  >         You are proposing the motion: {motion}.
  >         Come up with a clear argument in favor of the motion.
  >         Be very convincing.
  >     expected_output: >
  >         Your clear argument in favor of the motion, in a concise manner.
  >     agent: debater
  >     output_file: output/propose.md
  > ```
  >
