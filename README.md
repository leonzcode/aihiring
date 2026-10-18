# Racial Bias in AI Hiring Systems

A research paper on how AI hiring systems can disadvantage applicants because of their race. It covers the effects, the causes and possible fixes. It's built as an interactive web page with charts and a map.

**Read it:** [leonzhao.dev/apps/aihiring](https://leonzhao.dev/apps/aihiring/)

Featured in context at [leonzhao.dev/ai/aihiring](https://leonzhao.dev/ai/aihiring/).

## What's in it

The paper builds on the Bertrand & Mullainathan (2004) audit study. That's the original "Jamal vs. Greg" résumé experiment. It looks at three causes of bias in AI hiring:

1. The recent growth of AI in the hiring industry
2. Underrepresentation of minority groups in training datasets
3. The history behind racial discrimination in the United States

It then compares two fixes. Removing race and ethnicity signals from applications is the weak one. Mandatory bias audits are the strong one.

## Machine learning appendix

An appendix tests the argument on the original audit data (4,870 applications and 63 variables). Three models were trained and compared:

- Gradient boosted trees as a baseline
- A histogram GBM tuned with randomized search, with calibrated probabilities
- A PyTorch neural network ensemble (5-fold cross-validation over 3 seeds, so 15 networks averaged)

Permutation feature importance ranks race 7th of 60 features. Even among 59 other résumé features, race still has a measurable effect on the predictions.

## Built with

HTML, CSS and vanilla JavaScript. The charts use Chart.js and D3, and the US map uses TopoJSON. `images/_make_plot_04.py` regenerates one of the appendix figures.

## Run it locally

There's no build step. Open `index.html` in a browser, or serve the folder:

```bash
python -m http.server
```

Then go to http://localhost:8000. The chart libraries load from a CDN, so it needs an internet connection.
