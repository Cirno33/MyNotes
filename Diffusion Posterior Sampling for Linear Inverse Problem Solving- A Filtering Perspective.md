### Motivation

<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FUFL8A6I6%22%2C%22pageLabel%22%3A%221%22%2C%22position%22%3A%7B%22pageIndex%22%3A0%2C%22rects%22%3A%5B%5B340.34191777%2C527.8710784%2C468.13786665199996%2C536.5086526%5D%2C%5B143.865%2C516.9120783999999%2C468.1296973199992%2C525.5496526%5D%2C%5B143.865%2C505.95307840000004%2C468.12969731999914%2C514.5906526%5D%2C%5B143.865%2C494.9950784%2C469.78332951839957%2C503.6326526%5D%2C%5B143.865%2C484.0360784%2C393.07425844799945%2C492.67365259999997%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FBDG9PZNF%22%5D%2C%22locator%22%3A%221%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/UFL8A6I6?page=1">“Diffusion models provide powerful data priors that can solve linear inverse problems in zero shot through Bayesian posterior sampling. However, exact posterior sampling for diffusion models is intractable. Current solutions often hinge on approximations that are either computationally expensive or lack strong theoretical guarantees.”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FBDG9PZNF%22%5D%2C%22locator%22%3A%221%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/BDG9PZNF">Dou and Song, 2023, p. 1</a></span>)</span>

### Method

*   Linear Inverse Problems

Given a datapoint x, its lossy measurement is denoted as

![\<img alt="" data-attachment-key="LAUPHRIF" width="200" height="41" src="attachments/LAUPHRIF.png" ztype="zimage"> | 200](attachments/LAUPHRIF.png)![\<img alt="" data-attachment-key="RP28L75H" width="200" height="35" src="attachments/RP28L75H.png" ztype="zimage"> | 200](attachments/RP28L75H.png)

*   Bayesian filtering

![\<img alt="" data-attachment-key="MBTS3GEQ" width="894" height="94" src="attachments/MBTS3GEQ.png" ztype="zimage"> | 894](attachments/MBTS3GEQ.png)

The Bayesian filtering problem seeks to sample from the distribution $p(x_k | y_{1:k})$. Starting with the known prior distribution $p(x_0)$,

![\<img alt="" data-attachment-key="HZESQ8NL" width="1340" height="110" src="attachments/HZESQ8NL.png" ztype="zimage"> | 1340](attachments/HZESQ8NL.png)

![\<img alt="" data-attachment-key="QXKDAXRM" width="1078" height="166" src="attachments/QXKDAXRM.png" ztype="zimage"> | 1078](attachments/QXKDAXRM.png)

By iterating these two steps, we can solve the Bayesian filtering problem.

*   Filtering Posterior Sampling (FPS)

In diffusion posterior sampling problem,\
![\<img alt="" data-attachment-key="AAANN3ZC" width="300" height="46" src="attachments/AAANN3ZC.png" ztype="zimage"> | 300](attachments/AAANN3ZC.png)

![\<img alt="" data-attachment-key="KYXZ3S4M" width="1072" height="84" src="attachments/KYXZ3S4M.png" ztype="zimage"> | 1072](attachments/KYXZ3S4M.png)

Given $y ∼ N (Ax_0, σ^2I)$, it is easy to show that $y_k ∼ N (Ax_k, c^2_kσ^2I)$ for $c_k = a_1a_2 . . . a_k$.

Or generating $\{y_k\}$ from the backward process,

![\<img alt="" data-attachment-key="EINJHJQI" width="400" height="46" src="attachments/EINJHJQI.png" ztype="zimage"> | 400](attachments/EINJHJQI.png)

where $u_k$, $v_k$, $w_k$ can be computed from $a_k$, $b_k$, and the initial observation $y_N$ approximately follows $N (0, AA^⊤)$.

![\<img alt="" data-attachment-key="67RXY3KY" width="1586" height="92" src="attachments/67RXY3KY.png" ztype="zimage"> | 1586](attachments/67RXY3KY.png)

Since $p_θ(y_k | x_k) ∼ N (Ax_k, c^2_kσ^2I)$ and

![\<img alt="" data-attachment-key="RSS2STXN" width="1178" height="86" src="attachments/RSS2STXN.png" ztype="zimage"> | 1178](attachments/RSS2STXN.png)

![\<img alt="" data-attachment-key="CTNXRZ8B" width="300" height="26.363636363636363" src="attachments/CTNXRZ8B.png" ztype="zimage"> | 300](attachments/CTNXRZ8B.png)

we can get the posterior distribution,

![\<img alt="" data-attachment-key="64T6UTQ3" width="1276" height="102" src="attachments/64T6UTQ3.png" ztype="zimage"> | 1276](attachments/64T6UTQ3.png)

<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FUFL8A6I6%22%2C%22pageLabel%22%3A%226%22%2C%22position%22%3A%7B%22pageIndex%22%3A5%2C%22rects%22%3A%5B%5B107.691%2C312.0150784%2C504.0032279999991%2C320.65265259999995%5D%2C%5B108%2C301.05607840000005%2C203.19485469720004%2C309.6936526%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FBDG9PZNF%22%5D%2C%22locator%22%3A%226%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/UFL8A6I6?page=6">“To improve the approximation made by FPS, we propose a variant based on particle filtering and sequential Monte Carlo.”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FBDG9PZNF%22%5D%2C%22locator%22%3A%226%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/BDG9PZNF">Dou and Song, 2023, p. 6</a></span>)</span>

![\<img alt="" data-attachment-key="PGERY2ZX" width="2092" height="380" src="attachments/PGERY2ZX.png" ztype="zimage"> | 2092](attachments/PGERY2ZX.png)

![\<img alt="" data-attachment-key="TSNRATDV" width="2158" height="752" src="attachments/TSNRATDV.png" ztype="zimage"> | 2158](attachments/TSNRATDV.png)

![\<img alt="" data-attachment-key="4USYPNT3" width="1114" height="1204" src="attachments/4USYPNT3.png" ztype="zimage"> | 1114](attachments/4USYPNT3.png)
