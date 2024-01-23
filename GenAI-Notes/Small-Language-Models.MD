# Small Language Models— Efficient & Customizable

- Over the past few year, we have seen an explosion in artificial intelligence capabilities, much of which has been driven by advances in large language models (LLMs). Models like GPT-3, which contains 175 billion parameters, have shown the ability to generate human-like text, answer questions, summarize documents, and more. However, while the capabilities of LLMs are impressive, their massive size leads to downsides in efficiency, cost, and customizability. This has opened the door for an emerging class of models called Small Language Models (SLMs).

## What Are Small Language Models?

- Language models are AI systems trained on large text datasets which enable capabilities like generating text, summarizing documents, translating between languages, and answering questions. Small language models fill much of the same niche but with notably smaller model sizes. But what constitutes a small language model?

- Researchers typically consider language models under 100 million parameters to be relatively small, with some cutting off at even lower thresholds like 10 million or 1 million parameters. For comparison, models considered huge on today’s scale top over 100 billion parameters, like the aforementioned GPT-3 model from OpenAI.

- The smaller model sizes allow small language models to be more efficient, economical, and customizable than their largest counterparts. However, they achieve lower overall capabilities since model capacity in language models has been shown to correlate with size. Determining optimal model size for real-world applications involves navigating the tradeoffs between flexibility & customizability and sheer model performance.

## Motivations for Small Language Models

- As mentioned above, small language models come with inherent advantages in efficiency, cost, and customizability over their larger counterparts. Let’s break down each of these motivations in more detail:

### Efficiency

- Due to having fewer parameters, small language models are significantly more computationally efficient than massive models like GPT-3 in several regards:

    - They are faster in inference speed / throughput since fewer parameters need executing per input
    - They require less memory and storage space also owing to the overall smaller model size
    - Smaller datasets suffice for training small language models. As model capacity grows, the appetite for data grows with it.

### Cost

- Large language models require substantial computational resources to train and deploy. It’s estimated that developing GPT-3 cost OpenAI somewhere in the tens of millions of dollars accounting for hardware and engineering costs. Many of today’s publicly available large language models are not yet profitable to run due to their resource requirements.

- Meanwhile, small language models can readily be trained, deployed, and run on commodity hardware available to many businesses without breaking the bank. Their reasonable resource requirements open up applications in edge computing where they can run offline on lower-powered devices. Overall there’s greater potential to find profitable applications of small language models in the short-term.

### Customizability

- A key advantage that small language models maintain over their largest counterparts is customizability. While models like GPT-3 demonstrate strong versatility across many tasks, their capabilities still represent a compromise solution that balances performance across domains.

- Small language models on the other hand can readily be adapted to more narrow domains and specialized applications. With quicker iteration cycles, small language models make it practical to experiment with tailoring models to particular types of data through approaches like:

    - Pretraining — priming small models on domain-specific datasets
    - Fine-tuning — continuing training to optimize for end-task data
    - Prompt-based learning — optimizing model prompts for specialized applications
    - Architecture modifications — adapting model structure for niche tasks

- These sorts of customization processes become increasingly arduous for large models. Combined with their accessibility, small language models provide a codex that developers can mold to their particular needs.

## How Small can Useful Language Models be?

- Given the motivations to minimize model size covered above, a natural question arises — how far can we shrink down language models while still maintaining compelling capabilities? Recent research has continued probing the lower bounds of model scale required to complete different language tasks.

- Many investigations have found that modern training methods can impart basic language competencies in models with just 1–10 million parameters. For example, an 8 million parameter model released in 2023 attained 59% accuracy on the established GLUE natural language understanding benchmark.

- Performance continues rising as model capacity grows. A 2023 study found that across a variety of domains from reasoning to translation, useful capability thresholds for different tasks were consistently passed once language models hit about 60 million parameters. However, returns diminished after the 200–300 million parameter scale — adding additional capacity only led to incremental performance gains.

- These findings suggest even mid-sized language models hit reasonable competence across many language processing applications provided they are exposed to enough of the right training data. Performance then reaches a plateau where the vast bulk of compute and data seemingly provides little additional value. The sweet spot for commercially deployable small language models likely rests around this plateau zone balancing wide ability with lean efficiency.

- Of course, specialized small language models tuned deeply rather than broadly may require much less capacity to excel at niche tasks. We’ll cover some of those applied use cases later on. But first, let’s overview popular techniques for effectively training compact yet capable small language models.

## Training Methods for Efficient Small Language models

- The active progress training increasingly proficient small language models relies on methods that augment data efficiency and model utilization during the learning process. These techniques end up imparting more capability per parameter relative to naive training of larger models.

1. Transfer Learning

- Most modern language model training leverages some form of transfer learning where models bootstrap capability by first training on broad datasets before specializing to a narrow target domain. The initial pretraining phase exposes models to wide-ranging language examples useful for learning general linguistic rules and patterns.

- Small language models can capture much of this broad competency during pretraining despite having limited parameter budgets. Specialization phases then afford refinement towards specific applications without needing to expand model scale. Overall, transfer learning greatly improves data efficiency in training small language models.

2. Self-Supervised Learning

- Transfer learning training often utilizes self-supervised objectives where models develop foundational language skills by predicting masked or corrupted portions of input text sequences. These self-supervised prediction tasks serve as pretraining for downstream applications.

- Recent analysis has found that self-supervised learning appears particularly effective for imparting strong capabilities in small language models — more so than for larger models. By presenting language modelling as an interactive prediction challenge, self-supervised learning forces small models to deeply generalize from each data example shown rather than simply memorizing statistics passively. This engages fuller model capacity during training.

### Architecture Choices

- Not all neural network architectures are equivalently parameter-efficient for language tasks. Careful architecture selection focuses model capacity in areas shown to be critical for language modelling like attention mechanisms while stripping away less essential components.

- For example, Efficient Transformers have become a popular small language model architecture employing various techniques like knowledge distillation during training to improve efficiency. Relative to baseline Transformer models, Efficient Transformers achieve similar language task performance with over 80% fewer parameters. Effective architecture decisions amplify the ability companies can extract from small language models of limited scale.

- The techniques above have powered rapid progress, but there remain many open questions around how to most effectively train small language models. Identifying the best combinations of model scale, network design, and learning approaches to satisfy project needs will continue keeping researchers and engineers occupied as small language models spread to new domains.