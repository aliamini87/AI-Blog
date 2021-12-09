---
authors:
  - name: 
    email: 
    link:
    avatar: 
category:
date: 2021-10-14
description:
icon:
image: ..\static\shutterstock_250696570-Converted-1000x462.jpg
label: null
layout: default
order: 12
tags:
title:
visibility: public



---



# Intel open-sources AI-powered tool to spot bugs in code

![](https://venturebeat.com/wp-content/uploads/2021/09/GettyImages-1208499003-e1631641886627.jpg?zoom=2&resize=750%2C499&strip=all)

Intel today open-sourced [ControlFlag](https://venturebeat.com/2020/12/03/intels-controlflag-taps-ai-to-automatically-detect-errors-in-code/), a tool that uses machine learning to detect problems in computer code — ideally to reduce the time required to debug apps and software. In tests, the company’s machine programming research team says that ControlFlag has found hundreds of defects in proprietary, “production-quality” software, demonstrating its usefulness.

“Last year, ControlFlag identified a code anomaly in Client URL (cURL), a computer software project transferring data using various network protocols over one billion times a day,” Intel principal AI scientist Justin Gottschlich wrote in a [blog post](https://www.linkedin.com/pulse/newly-open-sourced-controlflag-identifies-hundreds-justin-gottschlich) on LinkedIn. “Most recently, ControlFlag achieved state-of-the-art results by identifying hundreds of latent defects related to memory and potential system crash bugs in proprietary production-level software. In addition, ControlFlag found dozens of novel anomalies on several high-quality open-source software repositories.”

The demand for quality code draws an ever-growing number of aspiring programmers to the profession. After years of study, they learn to translate abstracts into concrete, executable programs — but most spend the majority of their working hours not programming. A recent study found that the IT industry spent an estimated [$2 trillion in 2020](https://www.gartner.com/en/newsroom/press-releases/2020-01-15-gartner-says-global-it-spending-to-reach-3point9-trillion-in-2020) in software development costs associated with debugging code, with an estimated [50% of IT budgets spent on debugging](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.370.9611&rep=rep1&type=pdf).

ControlFlag, which works with any programming language containing control structures (i.e., blocks of code that specify the flow of control in a program), aims to cut down on debugging work by leveraging unsupervised learning. With unsupervised learning, an algorithm is subjected to “unknown” data for which no previously defined categories or labels exist. The machine learning system — ControlFlag, in this case — must teach itself to classify the data, processing the unlabeled data to learn from its inherent structure.

ControlFlag continually learns from unlabeled source code, “evolving” to make itself better as new data is introduced. While it can’t yet automatically mitigate the programming defects it finds, the tool provides suggestions for potential corrections to developers, according to Gottschlich.

“Intel is committed to making software more robust and less cumbersome to maintain while retaining excellent performance without introducing security vulnerabilities. We hope that projects like ControlFlag can substantially reduce the time it takes to develop software globally,” Gottschlich wrote. “Due to the overwhelming amount of time spent on debugging, even a small savings of time in this space could result in time and monetary savings and thereby allow us — as a community — to accelerate the advancement of technology.”

AI-powered coding tools like ControlFlag, as well as platforms like Tabnine, Ponicode, Snyk, and DeepCode, have the potential to reduce costly interactions between developers, such as Q&A sessions and repetitive code review feedback. [IBM](https://venturebeat.com/2021/05/10/ibms-codenet-dataset-aims-to-train-ai-to-tackle-programming-challenges/) and [OpenAI](https://venturebeat.com/2021/08/10/openai-launches-codex-an-api-for-translating-natural-language-into-code/) are among the many companies investigating the potential of machine learning in the software development space. But [studies](https://arxiv.org/pdf/2105.09938.pdf) have [shown](https://venturebeat.com/2021/07/18/openai-codex-shows-the-limits-of-large-language-models/) that AI has a ways to go before it can replace many of the manual tasks that human programmers perform on a regular basis.

___
source : [venturebit](https://venturebeat.com/2021/10/20/intel-open-sources-ai-powered-tool-to-spots-bugs-in-code/)
