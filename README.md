# Ollama Modelfile Template

This repository contains a comprehensive Modelfile template for creating and configuring models with Ollama. The template includes all possible instructions, fully commented out with detailed descriptions, allowing users to easily customize their model configurations.

## Overview

The Modelfile is a blueprint for creating and sharing models with Ollama. It specifies the base model, parameters, templates, and other settings necessary for model creation and operation. This template aims to provide a maximal setup, where all possible configurations are included and commented for ease of use.

## How to Use

1. **Clone the Repository**: First, clone this repository to your local machine using Git.

    ```bash
    git clone https://github.com/b1ip/ollama_modelfile_template.git
    ```

2. **Customize the Modelfile**: Navigate to the cloned repository and open the `Modelfile` in your favorite text editor. Uncomment and modify the necessary lines according to your specific requirements.

3. **Create Your Model**: Use the Ollama CLI to create a model with your customized Modelfile. Replace `choose-a-model-name` with your desired model name, and adjust the file path as necessary.

    ```bash
    ollama create choose-a-model-name -f ./Modelfile
    ```

4. **Run Your Model**: Once the model is created, you can run it using the Ollama CLI.

    ```bash
    ollama run choose-a-model-name
    ```

## Modelfile Instructions

## Detailed Parameter Descriptions

In the Modelfile, several instructions can be configured to customize the behavior of your Ollama models. Below is a breakdown of these instructions along with their specific parameters:

- **`FROM`**: Defines the base model to use for creating your customized model.

- **`PARAMETER`**:
  - `mirostat <0/1/2>`: Enable Mirostat sampling for perplexity control. `0` for disabled, `1` for Mirostat, and `2` for Mirostat 2.0.
  - `mirostat_eta <float>`: Learning rate for Mirostat, with a default of `0.1`, to adjust algorithm responsiveness.
  - `mirostat_tau <float>`: Balances between coherence and diversity, defaulting to `5.0`. Lower values yield more focused text.
  - `num_ctx <int>`: Context window size, default `2048`, controls tokens used for generating the next token.
  - `num_gqa <int>`: Number of GQA groups in the transformer layer, specific to some models like `llama2:70b`.
  - `num_gpu <int>`: Number of layers to process on the GPU(s), with macOS defaulting to `1` for Metal support.
  - `num_thread <int>`: Number of threads for computation, ideally matching the number of physical CPU cores.
  - `repeat_last_n <int>`: Lookback distance to prevent repetition, with `64` as the default, `0` disables, `-1` for `num_ctx`.
  - `repeat_penalty <float>`: Penalty for repetition, higher values enforce more variety, default `1.1`.
  - `temperature <float>`: Influences model creativity vs coherence, higher values for more creativity, default `0.8`.
  - `seed <int>`: Random seed for generation consistency, default `0`.
  - `stop "<string>"`: Stop sequences for ending generation, can be specified multiple times for different sequences.
  - `tfs_z <float>`: Tail free sampling for less probable tokens' impact reduction, default `1`, higher values reduce more.
  - `num_predict <int>`: Maximum tokens to predict, default `128`, `-1` for infinite, `-2` to fill context.
  - `top_k <int>`: Limits nonsense generation, higher values for more diversity, default `40`.
  - `top_p <float>`: Works with top-k for output diversity, higher values for more diversity, default `0.9`.

- **`TEMPLATE`**: Specifies the full prompt template to be sent to the model, including optional system messages, user prompts, and model responses.

- **`SYSTEM`**: Defines a custom system message to dictate the behavior of the chat assistant.

- **`ADAPTER`**: Applies (Q)LoRA adapters to the base model to modify its behavior or enhance its capabilities.

- **`LICENSE`**: Specifies the legal license under which the model is shared or distributed.

- **`MESSAGE`**: Sets up a predefined message history for the model to consider when generating responses, helping to provide context or guide the model's outputs.

Each instruction is explained in detail within the Modelfile comments.

## Contributing

Contributions to this template are welcome! Please submit a pull request or open an issue if you have suggestions for improvement.

## License

Specify the license under which this Modelfile template is shared. If not otherwise specified, consider the contents of this repository as covered under an open license, such as MIT or Apache 2.0.

## Additional Resources

- [Ollama Official Documentation](https://ollama.com/documentation)
- [Ollama GitHub Repository](https://github.com/jmorganca/ollama)

Please ensure to follow the official Ollama documentation and guidelines for the latest information and best practices.
