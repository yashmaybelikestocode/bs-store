# Rankle: a mini search engine ranked by link votes

Rankle is a small search engine that ranks web pages by **PageRank**. Every link to a page counts as a vote, and a vote from a trusted page counts for more. It shows why link votes beat the old way of ranking by how often a keyword appears.

**Run it:** open `index.html` in any browser.

## Features
- **Old way vs PageRank way:** side-by-side results for any search, so you can see keyword-stuffed fake sites win the old way and drop to the bottom with PageRank.
- **Real vs fake websites:** a "chance it's real" score for each page, based on PageRank and trusted inbound links.
- **Add your own fake websites:** stuff keywords and add link-farm pages, then watch PageRank ignore them.
- **Under the hood:** a diagram of which pages link to which, the PageRank formula, scores after each round, and a 100,000-move random-surfer simulation.
- **Editable link data** in the format `Page1->2,3`.

## The data
```
Page1->2        Page7->8
Page2->1,3      Page8->7,9,11
Page3->2,4      Page9->7,8
Page4->2,5      Page10->7     (fake pizza site)
Page5->2        Page11->7
Page6->1        (fake site)
```

## The formula
```
PR(A) = (1 − d)/N + d · Σ PR(B)/Out(B)      d = 0.85
```

The whole demo is one self-contained HTML file with no dependencies. Open `index.html` in any browser. All websites in the demo are fictional.
