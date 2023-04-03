# LLaMaBot: A Pythonic bot interface to LLMs

LLaMaBot implements a Pythonic interface to LLMs,
making it much easier to experiment with LLMs in a Jupyter notebook.
The model that we default to using is OpenAI's largest GPT-4 model.

## Install LLaMaBot

To install LLaMaBot:

```python
pip install llamabot
```

## How to use

### Obtain an OpenAI API key

Obtain an OpenAI API key and set it as the environment variable `OPENAI_API_KEY`.
(Here's a [reference][envvar] on what an environment variable is, if you're not sure.)

[envvar]: https://ericmjl.github.io/essays-on-data-science/software-skills/environment-variables/

We recommend setting the environment variable in a `.env` file
in the root of your project repository.
From there, `llamabot` will automagically load the environment variable for you.

### Simple Bot

The simplest use case of LLaMaBot is to create a simple bot that keeps no record of chat history.
This is useful for prompt experimentation,
or for creating simple bots that can be called upon repeatedly with different messages.
For example, to create a Bot that explains a given chunk of text like Richard Feynman would:

```python
from llamabot import SimpleBot

feynman = SimpleBot("You are Richard Feynman. You will be given a difficult concept, and your task is to explain it back.")
```

Now, `feynman` is callable on any arbitrary chunk of text and will return a rephrasing of that text in Richard Feynman's style (or more accurately, according to the style prescribed by the prompt).
For example:

```python
feynman("Enzyme function annotation is a fundamental challenge, and numerous computational tools have been developed. However, most of these tools cannot accurately predict functional annotations, such as enzyme commission (EC) number, for less-studied proteins or those with previously uncharacterized functions or multiple activities. We present a machine learning algorithm named CLEAN (contrastive learning–enabled enzyme annotation) to assign EC numbers to enzymes with better accuracy, reliability, and sensitivity compared with the state-of-the-art tool BLASTp. The contrastive learning framework empowers CLEAN to confidently (i) annotate understudied enzymes, (ii) correct mislabeled enzymes, and (iii) identify promiscuous enzymes with two or more EC numbers—functions that we demonstrate by systematic in silico and in vitro experiments. We anticipate that this tool will be widely used for predicting the functions of uncharacterized enzymes, thereby advancing many fields, such as genomics, synthetic biology, and biocatalysis.")
```

### Chat Bot

To experiment with a Chat Bot in the Jupyter notebook, we also provide the ChatBot interface.
This interface automagically keeps track of chat history for as long as your Jupyter session is alive.
Doing so allows you to use your own local Jupyter notebook as a chat interface.

For example:

```python
from llamabot import ChatBot

feynman = ChatBot("You are Richard Feynman. You will be given a difficult concept, and your task is to explain it back.")
feynman("Enzyme function annotation is a fundamental challenge, and numerous computational tools have been developed. However, most of these tools cannot accurately predict functional annotations, such as enzyme commission (EC) number, for less-studied proteins or those with previously uncharacterized functions or multiple activities. We present a machine learning algorithm named CLEAN (contrastive learning–enabled enzyme annotation) to assign EC numbers to enzymes with better accuracy, reliability, and sensitivity compared with the state-of-the-art tool BLASTp. The contrastive learning framework empowers CLEAN to confidently (i) annotate understudied enzymes, (ii) correct mislabeled enzymes, and (iii) identify promiscuous enzymes with two or more EC numbers—functions that we demonstrate by systematic in silico and in vitro experiments. We anticipate that this tool will be widely used for predicting the functions of uncharacterized enzymes, thereby advancing many fields, such as genomics, synthetic biology, and biocatalysis.")
```

With the chat history available, you can ask a follow-up question:

```python
feynman("Is there a simpler way to rephrase the text?")
```

And your bot will work with the chat history to respond.

## Contributing

### New features

New features are welcome!
These are early and exciting days for users of large language models.
Our development goals are to keep the project as simple as possible.
Features requests that come with a pull request will be prioritized;
the simpler the implementation of a feature (in terms of maintenance burden),
the more likely it will be approved.

### Bug reports

Please submit a bug report using the issue tracker.

### Questions/Discussions

Please use the Discussions feature on GitHub.

## Contributors

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->