# HF-LLM.rs 🦀

## WARNING

This repository is a fork of the original one ([HF-LLM.rs 🦀](https://github.com/Vaibhavs10/hf-llm.rs)). The only changes concern the details about **installation on Windows**.

## About 

HF-LLM.rs is a CLI tool for accessing Large Language Models (LLMs) like Llama 3.1, Mistral, Gemma 2, Cohere and much more hosted on Hugging Face. It allows you to interact with various models, provide input, and receive responses in a terminal environment.

Also, you can find the list of models supported by this CLI [here](https://huggingface.co/models?inference=warm&pipeline_tag=text-generation&sort=trending)—the list keeps getting updated as new models are released on the Hugging Face Hub. You might require a [Pro subscription](https://huggingface.co/subscribe/pro) to access some models.

## Features

- **Model Selection**: Choose from a variety of models available & deployed on Hugging Face infrastructure.
- **Input Prompt**: Provide an input prompt to generate responses.
- **Streaming Output**: Receive responses in real-time as the model generates output.
- **Chat Mode**: Start an interactive chat session with the LLM.

## Installation on Windows

1. **Open a Terminal**
   - Command Prompt (Windows 10 & 11) from the menu that appears after pressing Win+X or right-clicking the Start Menu.

2. **Install git**
- [Guide on how to install Git on Windows](https://www.simplilearn.com/tutorials/git-tutorial/git-installation-on-windows)
- Download the [latest version of Git](https://git-scm.com/downloads) and choose the 64/32 bit version.
- Check the installation: 
   ```
   git --version
   ```
3. **Install Rust (in order to install cargo)**
- [Guide on how to install Rust on Windows](https://www.rust-lang.org/tools/install): in the Rust development environment, all tools are installed to the ~/.cargo/bin directory, and this is where you will find the Rust toolchain, including rustc, **cargo**, and rustup. ([another installation guide about Rust](https://doc.rust-lang.org/cargo/getting-started/installation.html))
-  Accordingly, it is customary for Rust developers to include this directory in their PATH environment variable. During installation rustup will attempt to configure the PATH. Because of differences between platforms, command shells, and bugs in rustup, the modifications to PATH may not take effect until the console is restarted, or the user is logged out, or it may not succeed at all. If, after installation, running `rustc --version` in the console fails, this is the most likely reason. 
- Check the installation: 
   ```
   rustc --version
   ```

4. **Install HuggingFace Command Line Interface (CLI)**
   - [Guide on how to install HuggingFace Command Line Interface (CLI)](https://huggingface.co/docs/huggingface_hub/en/guides/cli)
   ```
   pip install -U "huggingface_hub[cli]"
   ```
   
   Check the installation:
   ```
   huggingface-cli --help
   ```

   Run the command:
   ```
   huggingface-cli login
   ```
   - Go to your HuggingFace profile and create a token in [Access Tokens](https://huggingface.co/settings/tokens)
   - Copy the token and paste it into the Terminal. Then, click on `Enter`.
      
5. **Clone the repository**
   - Navigate to the directory of your choice (command : `cd` if exists and/or `mkdir` if not) and clone the hf-llm.rs repository:
   ```
   git clone https://github.com/vaibhavs10/hf-llm.rs.git
   ```

6. **Navigate to the project directory**
   ```
   cd hf-llm.rs
   ```

7. **Build the project**
   ```
   cargo build --release
   ```

8. **Verify the installation**
   ```
   cargo run --release -- --help
   ```

## Usage

To use HF-LLM.rs, follow these steps:

1. **Open a Terminal**
   - Command Prompt (Windows 10 & 11) from the menu that appears after pressing Win+X or right-clicking the Start Menu.

2. **Login To Hugging Face with a valid token**
   Run the command:
   ```
   huggingface-cli login
   ```
   - Go to your HuggingFace profile and create a token in [Access Tokens](https://huggingface.co/settings/tokens)
   - Copy the token and paste it into the Terminal. Then, click on `Enter`.

3. **Navigate to the project directory**
   ```
   cd hf-llm.rs
   ```
   
4. **Launch the LLM model**
   Run the command:
   ```
   cargo run --release -- -m "meta-llama/Meta-Llama-3.1-70B-Instruct" -p "How to make a dangerously spicy ramen?"
   ```
   
   You can also use the chat mode to start an interactive chat session with the LLM.
   
   ```
   cargo run --release -- -m "meta-llama/Meta-Llama-3.1-70B-Instruct" -c
   ```

Note: Make sure to run `huggingface-cli login` to log into your Hugging Face account to access some of the models.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
