### Motivation

<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FFGKV5VE8%22%2C%22pageLabel%22%3A%221%22%2C%22position%22%3A%7B%22pageIndex%22%3A0%2C%22rects%22%3A%5B%5B373.74223539200017%2C451.21507840000004%2C469.78424981760026%2C459.8526526%5D%2C%5B143.866%2C440.30607840000005%2C468.13209208399985%2C448.9436526%5D%2C%5B143.866%2C429.3970784%2C244.273765222%2C438.03465259999996%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FJ3X9V429%22%5D%2C%22locator%22%3A%221%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/FGKV5VE8?page=1">“However, these achievements have primarily depended on task-specific conditional training or error-prone heuristic approximations.”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FJ3X9V429%22%5D%2C%22locator%22%3A%221%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/J3X9V429">Wu et al., 2024, p. 1</a></span>)</span>

*   **特定于任务的条件训练:** 需要为每个新的条件类型重新训练模型，成本高昂且不灵活。
*   **启发式近似方法:** 这些方法虽然灵活，可以直接用于预训练的无条件模型，但其近似的准确性未知，可能导致与条件不符或与模型先验不符的结果，尤其在需要高精度的领域（如分子设计）中存在风险。

### Method

*   twisting:

![\<img alt="" data-attachment-key="UK36HT4N" width="2128" height="132" src="attachments/UK36HT4N.png" ztype="zimage"> | 2128](attachments/UK36HT4N.png)

由于$p_\theta(y|x^t)$ intractable，用DM估计的$x^0$近似，

![\<img alt="" data-attachment-key="B6PBR7M9" width="1584" height="114" src="attachments/B6PBR7M9.png" ztype="zimage"> | 1584](attachments/B6PBR7M9.png)

类似classifier guidance，需要计算梯度，因此twisting functions需要differentiable；得到proposals如下，

![\<img alt="" data-attachment-key="DG3F3SAT" width="1770" height="178" src="attachments/DG3F3SAT.png" ztype="zimage"> | 1770](attachments/DG3F3SAT.png)

*   weighting functions

Because $\tilde{p}_θ(x^t | x^{t+1}, y)$ will not in general coincide with the optimal twisted proposal $p_θ(x^t | x^{t+1})$, we must introduce non-trivial weighting functions to ensure the resulting SMC sampler converges to the desired final target.

![\<img alt="" data-attachment-key="RFRV3FI4" width="1828" height="162" src="attachments/RFRV3FI4.png" ztype="zimage"> | 1828](attachments/RFRV3FI4.png)

![\<img alt="" data-attachment-key="W97JRDBE" width="200" height="26.82445759368836" src="attachments/W97JRDBE.png" ztype="zimage"> | 200](attachments/W97JRDBE.png)

### Experiments

*   二维模拟
*   条件图像生成
*   蛋白质 motif-scaffolding problem
