# Sentiment-Analysis-on-FOMC-meeting-minutes-with-FinBERT
This project utilize FinBert to extract the sentiment of Federal Open Market Committee meeting minutes and hope to discover relationship between sentiment of the minutes and stock market performance.

# Methodology
This project first start with obtaining FOMC meeting minutes with FedTools package. After obtaining the minutes, divide each minutes into sentences, then use FinBert to classify sentences into positive, neutral, or negative sentences. Next, evaluate the positiveness of each minutes by calculating the number of positive sentences minus the number of negative sentences then divide the whole number by the total number of sentences in the minute. Lastly, discover how the positiveness calculated affect the stock market performance.

# Effectiveness of the FinBERT model
