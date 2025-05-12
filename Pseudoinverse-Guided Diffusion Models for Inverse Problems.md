### Motivation

<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FU4F7LKFQ%22%2C%22pageLabel%22%3A%221%22%2C%22position%22%3A%7B%22pageIndex%22%3A0%2C%22rects%22%3A%5B%5B186.83369380000005%2C555.4060784000001%2C468.13766739999966%2C564.0436526000001%5D%2C%5B143.86500000000004%2C544.4470784000001%2C468.13766739999954%2C553.0846526000001%5D%2C%5B143.86500000000004%2C533.4880784000002%2C358.3697406%2C542.1256526000002%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FNQ9RQ6SI%22%5D%2C%22locator%22%3A%221%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/U4F7LKFQ?page=1">“Models trained for specific inverse problems work well but are limited to their particular use cases, whereas methods that use problem-agnostic models are general but often perform worse empirically.”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FNQ9RQ6SI%22%5D%2C%22locator%22%3A%221%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/NQ9RQ6SI">Song et al., 2022, p. 1</a></span>)</span>

### Method

*   Linear Inverse Problems

![\<img alt="" data-attachment-key="VM3TEGLZ" width="200" height="46.857142857142854" src="attachments/VM3TEGLZ.png" ztype="zimage"> | 200](attachments/VM3TEGLZ.png)

其中，$z ∼ N (0, σ^2_yI)$

*   Score function

The problem-specific score can be decomposed via Bayes’ rule:

![\<img alt="" data-attachment-key="584ESBCQ" width="1160" height="100" src="attachments/584ESBCQ.png" ztype="zimage"> | 1160](attachments/584ESBCQ.png)

![\<img alt="" data-attachment-key="773Z492C" width="350" height="62.8428927680798" src="attachments/773Z492C.png" ztype="zimage"> | 350](attachments/773Z492C.png)

We first approximate $p_t(x_0|x_t)$ with the following Gaussian:

![\<img alt="" data-attachment-key="E5SM7J4U" width="300" height="46.236559139784944" src="attachments/E5SM7J4U.png" ztype="zimage"> | 300](attachments/E5SM7J4U.png)

![\<img alt="" data-attachment-key="RXZPK5ID" width="1278" height="94" src="attachments/RXZPK5ID.png" ztype="zimage"> | 1278](attachments/RXZPK5ID.png)

$r_t$ is a timedependent standard deviation value that should depend on the data.

![\<img alt="" data-attachment-key="R8X22DNR" width="400" height="48" src="attachments/R8X22DNR.png" ztype="zimage"> | 400](attachments/R8X22DNR.png)

Thus, we have the following approximation to the score:

![\<img alt="" data-attachment-key="MAE2U29M" width="1454" height="212" src="attachments/MAE2U29M.png" ztype="zimage"> | 1454](attachments/MAE2U29M.png)

*   Adaptive weighting

<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FU4F7LKFQ%22%2C%22pageLabel%22%3A%225%22%2C%22position%22%3A%7B%22pageIndex%22%3A4%2C%22rects%22%3A%5B%5B149.16546320000018%2C495.5790784%2C504.00338739999944%2C504.2166526%5D%2C%5B108.00000000000017%2C484.6200784%2C468.5863443999995%2C493.2576526%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FNQ9RQ6SI%22%5D%2C%22locator%22%3A%225%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/U4F7LKFQ?page=5">“unlike most existing methods that apply a fixed weight for different diffusion times, we introduce a heuristic that implicitly adapts the guidance weights according to the timestep”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FNQ9RQ6SI%22%5D%2C%22locator%22%3A%225%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/NQ9RQ6SI">Song et al., 2022, p. 5</a></span>)</span>

![\<img alt="" data-attachment-key="6GR7CZHA" width="500" height="54.651162790697676" src="attachments/6GR7CZHA.png" ztype="zimage"> | 500](attachments/6GR7CZHA.png)
