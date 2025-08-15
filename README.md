# green-software-demos-
Tools and scripts for demonstrating the energy consumption of software.
All demos have been tested on a macOS machine.

Available demos:
- Fibonacci
- Large Language Models

Contact point: [Ivano Malavolta](https://www.ivanomalavolta.com)

## Fibonacci

1. Move into the `fibonacci` folder 
   ```
   cd ./fibonacci
   ```

2. Show and discuss the contents of the three scripts to the audience using your preferred Python editor
  - `fibonacci_rec.py` is a by-the-book recursive algorithm for computing the Fibonacci sequence of a given number  
  - `fibonacci_iter.py` is a basic iterative algorithm for computing the Fibonacci sequence of a given number
  - `fibonacci_mem.py` is an enhanced implementation of the recursive algorithm with [memoization](https://en.wikipedia.org/wiki/Memoization)

    In terms of execution time (and also energy consumption), `fibonacci_mem.py` < `fibonacci_rec.py` < `fibonacci_iter.py` (which is extremely slow).

3. Start the [macmon](https://github.com/vladkens/macmon) energy profiler
   ```
   macmon
   ```
   Any other profiler works as well, e.g., powermetrics.
   Here, discuss also the main metrics supported by the energy profiler. In the case of macmon, it is important to describe the *Total power* metric and how the power is consumed differently by the CPU and the GPU.  

5. Go into split view and show two terminal windows, in the first one, you continue showing the macmon dashboard, whereas in the second one you will execute, one by one, the three Python scripts using a command like:
   ```
   python fibonacci_rec.py
   ```
   Depending on the Fibonacci script being executed, the audience will see that the instantaneous power usage spikes with different durations.

## Large Language Models

