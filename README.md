# RecursiveAICoder

An experiment in letting a model write code, run it, and keep improving it with no human in between.

`main.py` asks a small local model (Gemma 2B through Ollama) to write a text-based game in Python, saves it to `generated_script.py` and runs it. Then, five times over, it gives the model everything it has written so far, asks it to make the game better, and runs each new version, printing the code and whatever it outputs (or the traceback if it crashed). Feeding those errors back to the model is the obvious next step.

`generated_script.py` is a real output: a short choose-your-path cave game.

## Files

| File | What it is |
|---|---|
| `main.py` | The full write, run, improve loop |
| `main2.0.py` | A cut-down version that generates one script and strips the Markdown code fence the model wraps around it |
| `testAI.py` | A quick check that Ollama is responding |
| `generated_script.py` | Example output |

## Running it

```bash
pip install ollama
ollama pull gemma:2b
python main.py
```

It runs whatever code the model writes, so use it in a folder you don't care about.
