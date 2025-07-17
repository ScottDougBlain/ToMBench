# ToMBench: Theory of Mind Evaluation Benchmark for Large Language Models

A comprehensive benchmark for evaluating Theory of Mind (ToM) capabilities in Large Language Models, with special emphasis on AI safety and alignment scenarios.

## Overview

ToMBench is a novel evaluation dataset designed to test LLMs' ability to reason about beliefs, knowledge states, and nested mental models. The benchmark includes 286 carefully crafted scenarios spanning social cognition, AI deployment contexts, and ethical decision-making.

## Dataset Structure

The dataset is provided as a CSV file (`ToM_Bench.csv`) with the following columns:

- **Scenario Name**: Descriptive title of the scenario
- **Scenario Text**: Detailed narrative setup
- **Question Label**: Unique identifier (Q1A-Q14F)
- **Question Text**: The specific question being asked
- **A-E**: Multiple choice options
- **Correct**: The correct answer
- **Explanation**: Reasoning for the correct answer
- **NBD**: Nesting depth of belief attribution
- **DOM**: Domain category (SOC, OBJ, TMP, ETH)
- **PHEN**: Phenomenon tested (e.g., IRN for irony, CC for capability concealment)
- **ASD**: Additional scenario descriptor
- **QT**: Question type (FC=Factual, MB=Mental/Belief, META=Meta-reasoning)
- **DIFF**: Difficulty level (easy, hard, xtrm)

## Key Features

### Scenario Domains
- **Social Scenarios**: Pluralistic ignorance, sarcasm detection, rumor propagation
- **AI Safety Contexts**: Model deployment decisions, capability concealment, value alignment
- **Object Tracking**: Physical reasoning with belief updates
- **Ethical Dilemmas**: Privacy, self-harm prevention, medical advice boundaries

### Question Types
1. **Factual Comprehension (FC)**: Basic understanding of scenario events
2. **Mental State Attribution (MB)**: Reasoning about characters' beliefs
3. **Nested Belief Reasoning**: Multi-level belief attribution (e.g., "What does A think B believes C knows?")
4. **Meta-Reasoning (META)**: Questions about the boundary between narrative and reality

### Difficulty Levels
- **Easy**: Direct factual recall or first-order belief attribution
- **Hard**: Complex nested beliefs or subtle social reasoning
- **Extreme (xtrm)**: Meta-level reasoning or highly nested belief chains

## Usage

```python
import pandas as pd

# Load the dataset
df = pd.read_csv('ToM_Bench.csv')

# Filter by difficulty
hard_questions = df[df['DIFF'] == 'hard']

# Filter by domain
ai_safety_questions = df[df['DOM'] == 'SOC']

# Get questions with deep belief nesting
deep_nesting = df[df['NBD'] >= 3]
```

## Evaluation Protocol

1. Present the scenario text to the LLM
2. Ask the question with multiple choice options
3. Compare LLM response to the correct answer
4. (Optional) Request explanation and compare to provided reasoning

## Sample Scenario

**Pluralistic Ignorance in AI Deployment**: Five engineers test an AI tool and discover various flaws but hesitate to share concerns in a meeting, leading to potential deployment of an unsafe system.

## Applications

- Evaluating LLM theory of mind capabilities
- Testing social reasoning in AI systems
- Assessing AI safety understanding
- Benchmarking progress in machine social intelligence

## Citation

If you use ToMBench in your research, please cite:

```bibtex
@dataset{blain2025tombench,
  title={ToMBench: Theory of Mind Evaluation Benchmark for Large Language Models},
  author={Blain, Scott D.},
  year={2025},
  publisher={GitHub},
  url={https://github.com/ScottDougBlain/ToMBench}
}
```

## Author

**Scott D. Blain, PhD**  
Postdoctoral Scholar  
Department of Psychiatry and Behavioral Health  
The Ohio State University  

## License

GPL

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests with:
- Additional scenarios
- Improved explanations
- Bug fixes
- Analysis tools

## Acknowledgments

This work bridges insights from psychology, neuroscience, and AI safety research.
