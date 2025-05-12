### Motivation

<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FDDADDQMF%22%2C%22pageLabel%22%3A%221%22%2C%22position%22%3A%7B%22pageIndex%22%3A0%2C%22rects%22%3A%5B%5B393.5223799359994%2C479.13607840000003%2C468.48636213999913%2C487.7736526%5D%2C%5B143.866%2C468.22707840000004%2C469.79195090740035%2C476.8646526%5D%2C%5B143.866%2C457.31807840000005%2C393.5223799359994%2C465.9556526%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2F86FSSFV8%22%5D%2C%22locator%22%3A%221%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/DDADDQMF?page=1">“Rather than merely generating designs that are natural, we aim to optimize downstream reward functions while preserving the naturalness of these design spaces.”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2F86FSSFV8%22%5D%2C%22locator%22%3A%221%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/86FSSFV8">Li et al., 2024, p. 1</a></span>)</span>

<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FDDADDQMF%22%2C%22pageLabel%22%3A%221%22%2C%22position%22%3A%7B%22pageIndex%22%3A0%2C%22rects%22%3A%5B%5B397.1501610999994%2C457.31807840000005%2C468.13069731999923%2C465.9556526%5D%2C%5B143.866%2C446.4090784%2C469.79084527599986%2C455.22597939999997%5D%2C%5B143.866%2C435.5000784%2C469.38012195%2C444.3169794%5D%2C%5B143.866%2C424.5910784%2C334.2472611096%2C433.2286526%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2F86FSSFV8%22%5D%2C%22locator%22%3A%221%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/DDADDQMF?page=1">“Existing methods for achieving this goal often require “differentiable” proxy models (e.g., classifier guidance) or computationally-expensive fine-tuning of diffusion models (e.g., classifier-free guidance, RL-based fine-tuning).”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2F86FSSFV8%22%5D%2C%22locator%22%3A%221%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/86FSSFV8">Li et al., 2024, p. 1</a></span>)</span>

### Method

采样目标：

![\<img alt="" data-attachment-key="KDCZGZM5" width="1736" height="164" src="attachments/KDCZGZM5.png" ztype="zimage"> | 1736](attachments/KDCZGZM5.png)

定义采样过程：

![\<img alt="" data-attachment-key="7TDIPP6J" width="1038" height="176" src="attachments/7TDIPP6J.png" ztype="zimage"> | 1038](attachments/7TDIPP6J.png)

Value function：

![\<img alt="" data-attachment-key="MI3E83AE" width="1702" height="116" src="attachments/MI3E83AE.png" ztype="zimage"> | 1702](attachments/MI3E83AE.png)

![\<img alt="" data-attachment-key="6W7J3GNT" width="2138" height="272" src="attachments/6W7J3GNT.png" ztype="zimage"> | 2138](attachments/6W7J3GNT.png)

1）soft-value function

一种是训练：

其中采用了如下近似，

![\<img alt="" data-attachment-key="AWQMIU2I" width="2130" height="174" src="attachments/AWQMIU2I.png" ztype="zimage"> | 2130](attachments/AWQMIU2I.png)

事实上是下界，<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FDDADDQMF%22%2C%22pageLabel%22%3A%226%22%2C%22position%22%3A%7B%22pageIndex%22%3A5%2C%22rects%22%3A%5B%5B108%2C126.61807840000002%2C457.7011263336002%2C135.5744558%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2F86FSSFV8%22%5D%2C%22locator%22%3A%226%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/DDADDQMF?page=6">“However, when α is very small, the scaling of exp(r(·)/α) tends to be excessively large.”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2F86FSSFV8%22%5D%2C%22locator%22%3A%226%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/86FSSFV8">Li et al., 2024, p. 6</a></span>)</span>，为避免这个问题emprically的做法。

![\<img alt="" data-attachment-key="U743JVIV" width="2172" height="452" src="attachments/U743JVIV.png" ztype="zimage"> | 2172](attachments/U743JVIV.png)

另一种是直接用模型预测的$\hat{x}_0$：

![\<img alt="" data-attachment-key="W3675SBI" width="2150" height="342" src="attachments/W3675SBI.png" ztype="zimage"> | 2150](attachments/W3675SBI.png)

2\) 采样$p_{t-1}^{\star,\alpha}$

采用importance sampling

![\<img alt="" data-attachment-key="FZ2FLJ52" width="1504" height="216" src="attachments/FZ2FLJ52.png" ztype="zimage"> | 1504](attachments/FZ2FLJ52.png)

![\<img alt="" data-attachment-key="IKA9VVE5" width="1166" height="164" src="attachments/IKA9VVE5.png" ztype="zimage"> | 1166](attachments/IKA9VVE5.png)

![\<img alt="" data-attachment-key="CN22ST5T" width="2162" height="788" src="attachments/CN22ST5T.png" ztype="zimage"> | 2162](attachments/CN22ST5T.png)
