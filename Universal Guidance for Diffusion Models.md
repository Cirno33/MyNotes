### Motivation

<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FHERCSMV6%22%2C%22pageLabel%22%3A%221%22%2C%22position%22%3A%7B%22pageIndex%22%3A0%2C%22rects%22%3A%5B%5B75.366%2C575.0840784%2C269.51834431199995%2C583.7216526%5D%2C%5B75.366%2C563.1280783999999%2C271.16456433600007%2C571.7656526%5D%2C%5B75.366%2C551.1730784%2C269.680933944%2C559.8106526%5D%2C%5B75.366%2C539.2180784%2C196.962721032%2C547.8556526%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FEKHPN4MY%22%5D%2C%22locator%22%3A%221%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/HERCSMV6?page=1">“Typical diffusion models are trained to accept a particular form of conditioning, most commonly text, and cannot be conditioned on other modalities without retraining.”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FEKHPN4MY%22%5D%2C%22locator%22%3A%221%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/EKHPN4MY">Bansal et al., 2023, p. 1</a></span>)</span>

### Method

*   forward universal guidance

根据classifier guidance的做法，

![\<img alt="" data-attachment-key="XDJ46YND" width="1276" height="120" src="attachments/XDJ46YND.png" ztype="zimage"> | 1276](attachments/XDJ46YND.png)

将其改写，使得能够接受通用的指导函数和损失函数。

![\<img alt="" data-attachment-key="RDIAAA29" width="1316" height="146" src="attachments/RDIAAA29.png" ztype="zimage"> | 1316](attachments/RDIAAA29.png)

<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FHERCSMV6%22%2C%22pageLabel%22%3A%224%22%2C%22position%22%3A%7B%22pageIndex%22%3A3%2C%22rects%22%3A%5B%5B97.67265691200001%2C426.12708280000004%2C291.0941891679998%2C435.77945580000005%5D%2C%5B55.44%2C414.8670784%2C290.68886631999993%2C423.5046526%5D%2C%5B55.44%2C402.91207840000004%2C289.44052753599993%2C411.86845580000005%5D%2C%5B55.44%2C390.9570784%2C268.8189668%2C399.59465259999996%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FEKHPN4MY%22%5D%2C%22locator%22%3A%224%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/HERCSMV6?page=4">“directly replacing f_cl and l_ce with any off-theshelf guidance and loss functions does not work in practice, as f is most likely trained on clean images and fails to provide meaningful guidance when the input is noisy.”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FEKHPN4MY%22%5D%2C%22locator%22%3A%224%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/EKHPN4MY">Bansal et al., 2023, p. 4</a></span>)</span>

因此采用每一步预测的$\hat{Z}_0$代替$Z_t$，

![\<img alt="" data-attachment-key="QZHFIB3J" width="1212" height="126" src="attachments/QZHFIB3J.png" ztype="zimage"> | 1212](attachments/QZHFIB3J.png)

![\<img alt="" data-attachment-key="W39MEYWM" width="954" height="140" src="attachments/W39MEYWM.png" ztype="zimage"> | 954](attachments/W39MEYWM.png)

*   backward universal guidance

<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FHERCSMV6%22%2C%22pageLabel%22%3A%224%22%2C%22position%22%3A%7B%22pageIndex%22%3A3%2C%22rects%22%3A%5B%5B190.702076792%2C86.74207840000001%2C289.4447926759999%2C95.3796526%5D%2C%5B55.44%2C74.7870784%2C291.0961174828%2C83.42465259999999%5D%2C%5B307.44%2C712.8250783999999%2C541.4381615159995%2C721.4626526%5D%2C%5B307.44%2C700.8690783999999%2C541.4373246575999%2C709.5066525999999%5D%2C%5B307.44%2C688.9140784%2C541.4359059713998%2C697.8704558000001%5D%2C%5B307.44%2C676.9590784%2C541.4426944990001%2C685.5966526%5D%2C%5B307.44%2C665.0040783999999%2C345.61668319999995%2C673.6416525999999%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FEKHPN4MY%22%5D%2C%22locator%22%3A%224%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/HERCSMV6?page=4">“we observe that forward guidance sometimes over-prioritizes maintaining the “realness” of the image, resulting in an unsatisfactory match with the given prompt. Simply increasing the guidance strength s(t) is suboptimal, as this often results in instability as the image moves off the manifold faster than the denoiser can correct it.”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FEKHPN4MY%22%5D%2C%22locator%22%3A%224%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/EKHPN4MY">Bansal et al., 2023, p. 4</a></span>)</span>

<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FHERCSMV6%22%2C%22pageLabel%22%3A%224%22%2C%22position%22%3A%7B%22pageIndex%22%3A3%2C%22rects%22%3A%5B%5B371.5308005639998%2C611.2060783999999%2C541.4369660039993%2C619.8436525999999%5D%2C%5B307.44%2C599.2510784%2C541.4369660039993%2C607.8886526%5D%2C%5B307.44%2C586.6000828%2C541.6863528516002%2C596.2514558%5D%2C%5B307.44%2C575.3400783999999%2C447.420463%2C584.2964558%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FEKHPN4MY%22%5D%2C%22locator%22%3A%224%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/HERCSMV6?page=4">“The key idea of backward guidance is to optimize for a clean image that best matches the prompt based on z_0, and linearly translate the guided change back to the noisy image space at step t.”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FEKHPN4MY%22%5D%2C%22locator%22%3A%224%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/EKHPN4MY">Bansal et al., 2023, p. 4</a></span>)</span>

![\<img alt="" data-attachment-key="RISSCGL2" width="992" height="116" src="attachments/RISSCGL2.png" ztype="zimage"> | 992](attachments/RISSCGL2.png)

![\<img alt="" data-attachment-key="JDTBFTRS" width="1004" height="118" src="attachments/JDTBFTRS.png" ztype="zimage"> | 1004](attachments/JDTBFTRS.png)

*   Per-step Self-recurrence

<span class="highlight" data-annotation="%7B%22attachmentURI%22%3A%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FHERCSMV6%22%2C%22pageLabel%22%3A%224%22%2C%22position%22%3A%7B%22pageIndex%22%3A3%2C%22rects%22%3A%5B%5B307.44%2C170.42907839999998%2C541.4369660039993%2C179.0666526%5D%2C%5B307.44%2C158.4730784%2C541.4369660039991%2C167.1106526%5D%2C%5B307.44%2C146.51807839999998%2C541.436966003999%2C155.1556526%5D%2C%5B307.44%2C134.5630784%2C390.1395425999999%2C143.2006526%5D%5D%7D%2C%22citationItem%22%3A%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FEKHPN4MY%22%5D%2C%22locator%22%3A%224%22%7D%7D" ztype="zhighlight"><a href="zotero://open/library/items/HERCSMV6?page=4">“Unfortunately, when we apply our universal guidance to standard generation pipelines, we often find images with artifacts and strange behaviors that clearly separate them from natural images.”</a></span> <span class="citation" data-citation="%7B%22citationItems%22%3A%5B%7B%22uris%22%3A%5B%22http%3A%2F%2Fzotero.org%2Fusers%2F15510469%2Fitems%2FEKHPN4MY%22%5D%2C%22locator%22%3A%224%22%7D%5D%2C%22properties%22%3A%7B%7D%7D" ztype="zcitation">(<span class="citation-item"><a href="zotero://select/library/items/EKHPN4MY">Bansal et al., 2023, p. 4</a></span>)</span>

在采样$Z_{t-1}$之后，再进行加噪，重复k次，其中$\epsilon' \sim \mathcal{N}(0, \mathbf{I})$，

![\<img alt="" data-attachment-key="EF6CHMEP" width="1146" height="98" src="attachments/EF6CHMEP.png" ztype="zimage"> | 1146](attachments/EF6CHMEP.png)

### Experiments

只有定性实验。

*   Stable Diffusion

    *   CLIP Guidance
    *   Segmentation Map Guidance
    *   Face Recognition Guidance
    *   Object Location Guidance
    *   Style Guidance

*   ImageNet Diffusion

    *   CLIP Guidance
    *   Object Location Guidance
    *   Segmentation-Guided Inpainting
