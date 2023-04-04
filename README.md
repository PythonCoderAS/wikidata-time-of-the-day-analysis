# wikidata-time-of-the-day-analysis
Analyzing the time of the day properties on Wikidata


Data gotten from this SPARQL:

```sparql
SELECT DISTINCT ?item ?itemLabel WHERE {
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE]". }
  {
    SELECT DISTINCT ?item WHERE {
      ?item p:P31 ?statement0.
      ?statement0 (ps:P31) wd:Q1260524.
      ?item p:P4895 ?statement1.
      ?statement1 (psv:P4895/wikibase:quantityAmount) ?numericQuantity.
    }
  }
}
```