### shell script that takes output from machine sentiment code block (saved as `machine-text_sentiment.txt` and converts it to a `.tsv` file with appropriate headings)

`awk '{FS = ","; OFS = "\t"}; BEGIN{print "Compound\tNegative\tNeutral\tPositive"}; {print $1,$2,$3,$4}' machine-text_sentiment.txt > machine-text_sentiment.tsv`

`awk '{FS = ","; OFS = "\t"}; BEGIN{print "Compound\tNegative\tNeutral\tPositive"}; {print $1,$2,$3,$4}' human-text_sentiment.txt > human-text_sentiment.tsv`

### shell script that removes text from each cell of `machine-text_sentiment.tsv` and saves that to a clean `.tsv` file

`sed 's/compound://;s/neg://;s/neu://;s/pos://' machine-text_sentiment.tsv > machine-text_sentiment_clean.tsv`

`sed 's/compound://;s/neg://;s/neu://;s/pos://' human-text_sentiment.tsv > human-text_sentiment_clean.tsv`