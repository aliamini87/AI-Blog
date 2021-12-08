# Google Search Goes Multimodal




Google will upgrade its search engine with a new model that tracks the relationships between words, images, and, in time, videos — the first fruit of its latest research into multimodal machine learning and multilingual language modeling.  
**What’s new:** Early next year, Google will integrate a new architecture called Multitask Unified Model (MUM) into its traditional Search algorithm and Lens photo-finding system, [_VentureBeat_](https://venturebeat.com/2021/09/29/how-google-plans-to-improve-web-searches-with-multimodal-ai/?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--nlQXRW4-7X-ix91nIeK09eSC7HZEucHhs-tTrQrkj708vf7H2NG5TVZmAM8cfkhn20y50) reported. The new model will enable the search engines to break down complex queries (“I’ve hiked Mt. Adams and now I want to hike Mt. Fuji next fall. What should I do differently to prepare?”) into simpler requests (“prepare to hike Mt. Adams,” “prepare to hike Mt. Fuji,” “Mt. Fuji next fall”). Then it can combine results of the simpler requests into coherent results.  
**How it works:** [Announced](https://blog.google/products/search/introducing-mum/?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--nlQXRW4-7X-ix91nIeK09eSC7HZEucHhs-tTrQrkj708vf7H2NG5TVZmAM8cfkhn20y50) in May, MUM is a transformers-based natural language model. It’s based on Google’s earlier [T5](https://arxiv.org/abs/1910.10683?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--nlQXRW4-7X-ix91nIeK09eSC7HZEucHhs-tTrQrkj708vf7H2NG5TVZmAM8cfkhn20y50) that comprises around 110 billion parameters (compared to BERT’s 110 million, GPT-3’s 175 billion, and Google’s own Switch Transformer at 1.6 trillion). It was trained on a dataset of text and image documents drawn from the web from which hateful, abusive, sexually explicit, and misleading images and text were removed.

-   Google Search users will see three new features powered by MUM: an AI-curated list that turns broad queries into actionable items and step-by-step instructions, suggestions to tweak queries, and links to relevant audio and video results.
-   [Google Lens](https://lens.google/?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--nlQXRW4-7X-ix91nIeK09eSC7HZEucHhs-tTrQrkj708vf7H2NG5TVZmAM8cfkhn20y50) users can take a photo of a pair of boots and, say, ask if they are appropriate to hike a particular mountain. MUM will provide an answer depending on the type of boot and the conditions on the mountain.
-   The technology can answer queries in 75 languages and translate information from documents in a different language into the language of the query.
-   Beyond filtering objectionable material from the training set, the company tried to mitigate the model’s potential for harm by enlisting humans to evaluate its results for evidence of bias.

**Behind the news:** In 2019, Google Search integrated [BERT](https://blog.google/products/search/search-language-understanding-bert/?utm_campaign=The%20Batch&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--nlQXRW4-7X-ix91nIeK09eSC7HZEucHhs-tTrQrkj708vf7H2NG5TVZmAM8cfkhn20y50). The change improved the results of 10 percent of English-language queries, the company said, particularly those that included conversational language or prepositions like “to” (the earlier version couldn’t distinguish the destination country in a phrase like “brazil traveler to usa”).  BERT helped spur a trend toward larger, more capable transformer-based language models.  
**Why it matters:** Web search is ubiquitous, but there’s still plenty of room for improvement. This work takes advantage of the rapidly expanding capabilities of transformer-based models.  
**We’re thinking:** While we celebrate any advances in search, we found Google’s announcement short on technical detail. Apparently MUM really is the word.

---
source : [deeplearning.ai](https://read.deeplearning.ai/the-batch/issue-113/)
