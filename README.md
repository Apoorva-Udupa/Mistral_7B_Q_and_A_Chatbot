# Mistral_7B_Q_and_A_Chatbot


### Project Overview

The Mistral Chatbot project leverages the advanced capabilities of the Mistral 7B model, a state-of-the-art language model known for its efficiency and effectiveness in handling natural language understanding tasks. This chatbot is specifically trained to respond to inquiries related to the impacts of mobile device usage on human health and behavior.

## Technical Details

### Model: Mistral 7B

**Nature of Model:** Causal LLM (Language Model), distinct from sequence-to-sequence models, which makes it well-suited for generating coherent and contextually relevant text based on input queries.

### Training Data

**Dataset:** Alpaca dataset, a well-known conversational dataset, which includes diverse dialogues that enhance the model's ability to understand and generate human-like responses.

### Optimization and Training

- **Optimizer:** Paged AdamW with 32-bit precision, known for its efficiency in handling large models.
- **Learning Rate:** 0.0002 with a cosine learning rate scheduler to adjust the rate in a pre-defined cosine curve, optimizing the convergence rate over training epochs.
- **LoRA:** Used Low-Rank Adaptation (LoRA) with a rank of 16, which allows modification of specific parts of the model (targeting v_proj and q_proj) without retraining the entire network. This method is effective in adapting large models to new tasks with minimal computational overhead.
- **Training Steps:** Executed for 2000 steps with evaluations at every 100 steps to monitor progress and adjust parameters if necessary.
- **Mixed Precision Training:** Utilized FP16 (16-bit floating point precision) to speed up the training process while reducing memory consumption, enabling the training of large models on available hardware more efficiently.

### Performance

**Initial Training Losses:** Started at 1.4236 at step 100 and reduced to 1.2553 by step 200, indicating effective learning and adaptation by the model to the training data.

## Implementation Details

- **AutoTokenizer:** Employed to process input queries, ensuring that the text is correctly formatted and tokenized before being fed into the model.
- **Output Handling:** Designed to generate detailed responses that highlight various negative effects of mobile device usage, such as impacts on posture, sleep quality, memory retention, and social skills, among others.

## Application and Impact

This project exemplifies the application of advanced AI in creating responsive and insightful chatbot services. By focusing on the specific issue of mobile device impacts, the chatbot provides valuable information that aids users in understanding potential health and behavioral risks associated with prolonged usage of mobile devices.

