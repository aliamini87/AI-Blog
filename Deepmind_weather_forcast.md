---
authors:
  - name: 
    email: 
    link:
    avatar: 
category:
date: 2021-10-06
description:
icon:
image: ..\static\shutterstock_250696570-Converted-1000x462.jpg
label: null
layout: default
order: 3
tags:
title:
visibility: public

---


# DeepMind claims its AI weather forecasting model beats conventional models

In a paper published in the journal _Nature_, meteorologists gave an AI model for predicting short-term weather events top rank in terms of accuracy and usefulness in 88% of cases. It marks the first time professional forecasters have expressed a preference for a machine learning-based model over conventional methods, claims DeepMind, which developed the model — paving the way to new weather forecasting approaches that leverage AI.

While studies suggest some forms of machine learning contribute significantly to greenhouse gas emissions, the technology has also been proposed as a tool to _combat_ climate change. For example, an IBM [project](https://venturebeat.com/2020/04/29/researchers-propose-ways-to-apply-ai-to-agriculture-and-conservation/) delivers farm cultivation recommendations from digital farm “twins” that simulate the future weather and soil conditions of real-world crops. Other researchers are using AI-generated images to help [visualize](https://venturebeat.com/2019/10/23/researchers-visualize-climate-impact-with-ai-generated-images/) climate change and [estimate](https://venturebeat.com/2021/09/13/ai-can-estimate-corporate-greenhouse-gas-emissions/) corporate carbon emissions, and nonprofits like [WattTime](https://venturebeat.com/2020/09/11/ai-weekly-what-ml-practitioners-are-doing-about-climate-change/) are working to reduce households’ carbon footprint by automating when electric vehicles, thermostats, and appliances are active based on where renewable energy is available.

“Precipitation ‘nowcasting,’ the high-resolution forecasting of precipitation up to two hours ahead, supports the real-world socioeconomic needs of many sectors reliant on weather-dependent decision-making,” the DeepMind paper reads. “Skilful nowcasting is a longstanding problem of importance for much of weather-dependent decision-making. Our approach using deep generative models directly tackles this important problem, improves on existing solutions and provides the insight needed for real-world decision-makers.”

## Predicting weather events

“Nowcasting” is key to weather-dependent decision making because it informs the operations of emergency services, energy management, retail, flood early-warning systems, air traffic control, marine services, and more. But for nowcasting to be useful, the forecast must provide accurate predictions and account for uncertainty, including events that could greatly impact human life.

![DeepMind](https://venturebeat.com/wp-content/uploads/2021/09/fig1-wheel.gif?w=710&resize=710%2C300&strip=all)

Several approaches based on machine learning have been developed in recent years. Trained on large datasets of radar observations, they aim to better model heavy precipitation and other hard-to-predict precipitation phenomena. For example, Google partnered with the U.S. National Oceanic and Atmospheric Administration (NOAA) to study and develop [machine learning](https://venturebeat.com/category/ai/) systems that might be infused across NOAA’s enterprise. Microsoft has also funded [efforts](https://blogs.microsoft.com/ai/ai-subseasonal-weather-forecast/) to identify repeating weather and climate patterns from historical data as a way to improve subseasonal and seasonal forecast models.

But DeepMind notes that AI nowcasting models don’t always include small-scale weather patterns or provide forecasts over entire regions. As an alternative, the Alphabet-backed company created a deep generative model (DGM) for forecasting, which learned the probability distributions of data — functions that describe all the possible values a random variable could take — to generate “nowcasts” from its learned distributions.

![DeepMind weather](https://venturebeat.com/wp-content/uploads/2021/09/Screenshot-19.png?w=800&resize=800%2C269&strip=all)

Above: DeepMind’s AI model predicts weather events up to 90 minutes in advance.

_Image Credit: DeepMind_

DeepMind asserts that DGMs can predict weather events events that are inherently difficult to track due to the underlying randomness. Moreover, they can anticipate the location of precipitation as accurately as systems tuned to the task while preserving properties useful for decision-making.

DeepMind trained its DGM on a large dataset of precipitation events recorded by radar in the U.K. between 2016 and 2018. Once trained, it could deliver nowcasts in just over a second running on a single NVIDIA V100 GPU.

When compared to other popular nowcasting approaches, including other machine learning models, DeepMind’s DGM — judged by a panel of 56 meteorologists — produced more realistic and consistent predictions over regions up to 1,536 kilometers by 1,280 kilometers and with lead times from 5 to 90 minutes ahead.

“Using a systematic evaluation by more than 50 expert meteorologists, we show that our generative model ranked first for its accuracy and usefulness in 89% of cases against two competitive methods,” the paper reads. “We show that generative nowcasting can provide probabilistic predictions that improve forecast value and support operational utility, and at resolutions and lead times where alternative methods struggle.”

## Real-world applications

DeepMind’s model and others like it are emerging at a time when climate change is top of mind for the world’s largest companies. As a CDP analysis recently found, 500 of the biggest corporations potentially face roughly $1 trillion in costs related to climate change in the decades ahead unless they take proactive steps to prepare.

Previous studies [have estimated](https://www.nature.com/articles/nclimate2972) that the risks of global warming, if left unmanaged, could cost the world’s financial sector between $1.7 trillion to $24.2 trillion. In one stark example, Pacific Gas and Electric, California’s largest electric utility, faced up to $30 billion in January 2019 in fire liabilities alone.

Facebook chief AI scientist Yann LeCun and Google Brain cofounder Andrew Ng, among others, have asserted that mitigating [climate change](https://venturebeat.com/2019/12/16/ai-experts-urge-machine-learning-researchers-to-tackle-climate-change/) and promoting [energy efficiency](https://venturebeat.com/2019/12/17/yann-lecun-ar-glasses-will-be-the-killer-app-of-energy-efficient-machine-learning/) are worthy challenges for AI researchers.

“The ability to model complex phenomena, make fast predictions and represent uncertainty makes AI a powerful tool for environmental scientists, including those studying the impacts of climate change,” DeepMind senior staff scientist Shakir Mohamed said in a press release. “It’s very early days, but this trial shows that AI could be a powerful tool, enabling forecasters to spend less time trawling through ever growing piles of prediction data and instead focus on better understanding the implications of their forecasts. This will be integral for mitigating the adverse effects of climate change today, supporting adaptation to changing weather patterns and potentially saving lives.”

---

Source: [Venturebeat](https://venturebeat.com/2021/09/29/deepmind-claims-its-ai-weather-forecasting-model-beats-conventional-models/)
