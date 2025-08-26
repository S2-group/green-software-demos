# green-software-demos
Tools and scripts for demonstrating the energy consumption of software.
All demos have been tested on a macOS machine.

Available demos:
- [Fibonacci](#fibonacci)
- [Large Language Models](#large-language-models)

## Fibonacci

1. Move into the `fibonacci` folder 
   ```
   cd ./fibonacci
   ```

2. Show and discuss the contents of the three scripts to the audience using your preferred Python editor (all scripts compute and print the first 10,000 numbers of the Fibonacci sequence):
  - `fibonacci_rec.py` is a by-the-book recursive algorithm for computing the Fibonacci sequence of a given number  
  - `fibonacci_iter.py` is a basic iterative algorithm for computing the Fibonacci sequence of a given number
  - `fibonacci_mem.py` is an enhanced implementation of the recursive algorithm with [memoization](https://en.wikipedia.org/wiki/Memoization)

    In terms of execution time (and also energy consumption), `fibonacci_mem.py` < `fibonacci_rec.py` < `fibonacci_iter.py` (which is extremely slow).

    Thanks to [Mandy Wong](https://github.com/mandymay138) for the implementation of the [three Fibonacci algorithms]((https://realpython.com/fibonacci-sequence-python/)) used in this demo! 

3. Start the [macmon](https://github.com/vladkens/macmon) energy profiler
   ```
   macmon
   ```
   Any other profiler works as well, e.g., _powermetrics_.
   Here, discuss also the main metrics supported by the energy profiler. In the case of macmon, it is important to describe the __Total power__ metric and how the power is consumed differently by the CPU and the GPU.  

4. Go into split view and show two terminal windows, in the first one, you continue showing the _macmon_ dashboard, whereas in the second one you will execute, one by one, the three Python scripts using a command like:
   ```
   python fibonacci_rec.py
   ```
   Depending on the Fibonacci script being executed, the audience will see that the instantaneous power usage spikes with different durations.

## Large Language Models

1. [Download](https://ollama.com/download/) and install [Ollama](https://ollama.com/). This will be the engine for downloading and running your LLMs

2. Check that your Ollama installation succeeded by running this:
   ```
   ollama
   ```
   This should show simple help instructions about Ollama

3. Load at least two LLMs into Ollama (see the full list [here](https://ollama.com/models), in the example below we will load four of them:
   ```
   ollama pull gpt-oss:latest
   ollama pull llama3.3:latest
   ollama pull deepseek-r1:1.5b
   ollama pull deepseek-r1:14b

   ollama list # this is to check if all models have been correctly pulled from the cloud
   ```
   Choose LLMs that are different in terms of vendor (e.g., Open AI vs Meta vs DeepSeek in this case) and size in terms of parameter (e.g., 1.5B vs 14B for Deepseek in this case). This will help in better explaining the differences in power consumption that will emerge during the execution of the models in step 5.

   It is important that points 1, 2, and 3 are all executed before going on stage, point 3 might take a considerable amount of time, depending on the size of the models to download.

4. Start the [macmon](https://github.com/vladkens/macmon) energy profiler
   ```
   macmon
   ```
   Any other profiler works as well, e.g., _powermetrics_.
   Here, discuss also the main metrics supported by the energy profiler. In the case of macmon, it is important to describe the __Total power__ metric and how the power is consumed differently by the CPU and the GPU.  

5. Go into split view and show two terminal windows, in the first one, you continue showing the _macmon_ dashboard, whereas in the second one you will execute one of the LLMs with the following command:
   ```
   ollama run gpt-oss:latest
   ```
   Afterwards, you will make a series of prompts, directly in the terminal. Now the audience will see the output tokens being produced by the LLM and at the same time, they will see the instantaneous power usage of the GPU spiking.
   At the end, stop the LLM by running the `\bye` command.
   
6. Repeat step 5, but with different LLMs. Depending on the used LLM and on the prompt being executed, the audience will see different spikes. You will discuss those observed differences and will try to map them to "real-world" quantities (e.g., a LED lightbulb typically consumes 10W).
      

## Contact point
[Ivano Malavolta](https://www.ivanomalavolta.com)
