# Sentiment Analysis on FOMC Meeting Minutes with FinBERT

## Overview
In the ever-evolving landscape of financial markets, understanding the subtle undercurrents of sentiment can be crucial. This project aims to deploy FinBERT, a state-of-the-art NLP model specialized for financial text, to scrutinize the sentiment embedded in the Federal Open Market Committee (FOMC) meeting minutes. The goal is to unearth relations between the sentiment expressed in these minutes and the performance of the stock market, potentially offering valuable insights for economists and investors alike.

## Methodology for sentiment analysis

### Data Acquisition
- **Source**: We leverage the `FedTools` package to systematically gather the FOMC meeting minutes.
- **Scope**: The analysis spans 2003 to 2023, covering a comprehensive array of economic conditions.

### Preprocessing
- **Sentence Segmentation**: Each document is meticulously broken down into individual sentences to prepare for fine-grained sentiment analysis.

### Sentiment Analysis with FinBERT
- **Model Introduction**: FinBERT is a transformer-based model specifically trained on financial texts, offering nuanced understanding beyond general-purpose language models.
- **Classification**: Each sentence is classified into one of three categories: positive, neutral, or negative.

### Sentiment Aggregation
- **Calculation**: To quantify the overall sentiment of each meeting's minutes, we calculate a sentiment score: `(Number of Positive Sentences - Number of Negative Sentences) / Total Number of Sentences`.

## Results
### Does the positiveness of FOMC minutes reflect SP500?
The core objective of this analysis was to decipher if there exists a tangible relationship between the sentiment (measured as 'positiveness') in the Federal Open Market Committee (FOMC) minutes and the performance of the S&P 500 stock market index.
![Sentiment and SP500](https://github.com/HaHaIamHarry/Sentiment-Analysis-on-FOMC-meeting-minutes-with-FinBERT/assets/141811361/97605fcd-bf32-4860-b291-04ea6a10d828)
The visualization provided spans two decades, from 2003 to 2023, and offers a concurrent view of two datasets:

S&P 500 Index (in Blue): This offers a macroscopic view of the stock market's health and is plotted on the left vertical axis.
Positiveness (in Orange): Extracted from the FOMC minutes, this sentiment score is visualized on the right vertical axis. A positive score indicates an optimistic tone in the minutes, while a negative score leans towards pessimism.
#### Observations:
Synchronized Movements: For vast durations, especially around 2005-2008 and 2018-2021, both metrics seem to move in harmony. Peaks in the S&P 500 Index are often matched with spikes in positiveness, while troughs coincide with more negative sentiment. This suggests that during bullish market conditions, FOMC minutes tend to be more upbeat, and conversely, during bearish times, a more cautious tone might prevail.

Divergences: It's vital to note that this correlation isn't consistent. Particularly around 2010-2013 and post-2022, the positiveness and the S&P 500 Index showcase some divergent behavior, indicating that external factors, possibly not covered by the sentiment of FOMC minutes, might have influenced the stock market's trajectory.

General Reflection: While the graph does not establish causality, the observed trends hint that the sentiment within FOMC minutes could serve as a potential leading or concurrent indicator of stock market performance.

#### Conclusion:
While the 'positiveness' derived from the FOMC minutes does echo certain trends in the S&P 500 Index over the years, investors and analysts should approach this correlation with caution. The stock market is influenced by a myriad of factors, with central bank communication being just one component. Further statistical testing would be crucial to determine the strength and significance of this relationship. However, the presented analysis opens the door for a more in-depth exploration into the interplay between central bank communications and financial markets.

### How does positiveness of FOMC affect future return of SP500?
The scatter plot visualizes the relationship between the sentiment, measured as 'positiveness', of Federal Open Market Committee (FOMC) minutes and the subsequent 6-month returns on the S&P 500 index. Key reference points on the graph include a red horizontal line, indicating 0% future return, and a green vertical line representing the threshold for negativity in sentiment, i.e., a positiveness score of -0.2.
![Positiveness and future return](https://github.com/HaHaIamHarry/Sentiment-Analysis-on-FOMC-meeting-minutes-with-FinBERT/assets/141811361/817e26de-feea-4037-806a-5f15714a7c6f)
#### Observations:

- **Distribution of Returns**: Points to the left of the green vertical line represent periods when the FOMC minutes conveyed a negative sentiment, i.e., a positiveness score less than -0.2. In these periods, the expected 6-month return was approximately 2.52%, compared to the average expected 6-month return under all sentiment of 4.76%.

- **Risk Profile**: The risk associated with returns, as measured by the standard deviation, is higher during periods of negative FOMC sentiment. Specifically, the standard deviation is approximately 16.43% for returns following negative sentiment minutes, compared to an average standard deviation under all sentiment of 10.81%.

- **Probability of Positive Returns**: When the sentiment in FOMC minutes is negative (below -0.2), the likelihood of realizing positive returns in the subsequent 6 months is 65.52%, compared to an average probability under all sentiment of 75%.

#### Statistics Table:

| Metric | Value When FOMC is Negative (Positiveness < -0.2) | Average Value Under All Sentiment |
|--------|----------------------------------------------------|-----------------------------------|
| Expected 6M Return | 2.52% | 4.76% |
| Standard Deviation of 6M Return | 16.43% | 10.81% |
| Probability of Positive 6M Return | 65.52% | 75% |

#### Conclusion:

The scatter plot and accompanying statistics underscore the influence of FOMC sentiment on short-term market performance. Periods of negative sentiment, as marked by positiveness scores below -0.2, correlate with lower expected returns, higher return volatility, and reduced chances of positive outcomes. While causality cannot be inferred directly from this analysis, it highlights the potential impact of central bank communications on investor sentiment and market movements. Investors should consider this relationship, among other factors, in their decision-making processes.

### Reference
Yi, Y. (2020, June 10). FinBERT-tone. Retrieved July 5, 2023, from https://huggingface.co/yiyanghkust/finbert-tone. <br>
Huang, A., Wang, H., & Yang, Y. (2023). FinBERT: A Large Language Model for Extracting Information from Financial Text. Retrieved July 5, 2023, from https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3910214 <br>
FedTools. (20223). Retrieved July 5, 2023, from https://pypi.org/project/Fedtools/
