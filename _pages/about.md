---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}
<style>
  body {
    font-size: 16px; /* 设置基础字体大小 */
  }
  
  /* 或者设置所有元素 */
  * {
    font-size: 16px;
  }
</style>

<span class='anchor' id='about-me'></span>


Hi~ I am a four-year PhD student in The Hong Kong Polytechnic University, advised by [Prof.Hu Haibo](https://haibohu.org/). Previously, I graduated from Jilin University with a bachelor’s degree and from Institute of Information Engineering, Chinese Academy of Sciences with a master’s degree.

<!-- Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet. Suspendisse condimentum, libero vel tempus mattis, risus risus vulputate libero, elementum fermentum mi neque vel nisl. Maecenas facilisis maximus dignissim. Curabitur mattis vulputate dui, tincidunt varius libero luctus eu. Mauris mauris nulla, scelerisque eget massa id, tincidunt congue felis. Sed convallis tempor ipsum rhoncus viverra. Pellentesque nulla orci, accumsan volutpat fringilla vitae, maximus sit amet tortor. Aliquam ultricies odio ut volutpat scelerisque. Donec nisl nisl, porttitor vitae pharetra quis, fringilla sed mi. Fusce pretium dolor ut aliquam consequat. Cras volutpat, tellus accumsan mattis molestie, nisl lacus tempus massa, nec malesuada tortor leo vel quam. Aliquam vel ex consectetur, vehicula leo nec, efficitur eros. Donec convallis non urna quis feugiat. -->

My research interest includes trustworthy machine learning, with a focus on privacy and security attacks. 
<!-- I have published more than 100 papers at the top international AI conferences with total <a href='https://scholar.google.com/citations?user=DhtAFkwAAAAJ'>google scholar citations <strong><span id='total_cit'>260000+</span></strong></a> (You can also use google scholar badge <a href='https://scholar.google.com/citations?user=DhtAFkwAAAAJ'><img src="https://img.shields.io/endpoint?url={{ url | url_encode }}&logo=Google%20Scholar&labelColor=f6f6f6&color=9cf&style=flat&label=citations"></a>). -->


# 🔥 News
- *2025.12*: &nbsp;🎉🎉 Our paper *United We Defend: Collaborative Membership Inference Defenses in Federated Learning* is accepted by USENIX Security 2026.
- *2025.09*: &nbsp;🎉🎉 Our paper *Toward Efficient Inference Attacks: Shadow Model Sharing via Mixture-of-Experts* is accepted by NeurIPS 2025.
<!-- - *2022.02*: &nbsp;🎉🎉 Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet.  -->

# 📝 Publications 

<!-- <div class='paper-box'><div class='paper-box-image'><div><div class="badge">CVPR 2016</div><img src='images/500x300.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Deep Residual Learning for Image Recognition](https://openaccess.thecvf.com/content_cvpr_2016/papers/He_Deep_Residual_Learning_CVPR_2016_paper.pdf)

**Kaiming He**, Xiangyu Zhang, Shaoqing Ren, Jian Sun

[**Project**](https://scholar.google.com/citations?view_op=view_citation&hl=zh-CN&user=DhtAFkwAAAAJ&citation_for_view=DhtAFkwAAAAJ:ALROH1vI_8AC) <strong><span class='show_paper_citations' data='DhtAFkwAAAAJ:ALROH1vI_8AC'></span></strong>
- Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet. 
</div>
</div> -->

<!-- - <strong>United We Defend: Collaborative Membership Inference Defenses in Federated Learning</strong><br>
  <span style="font-size: 0.95em;"> Li Jin, Yifeng Hong, et al. </span><br>
  <a href="https://arxiv.org/abs/2601.06866" style="color: #2196F3; text-decoration: none; margin-right: 10px;">
    <span style="background-color: #E3F2FD; padding: 2px 6px; border-radius: 4px;"> Paper</span>
  </a>
  <a href="https://github.com/BaiLibl/CoFedMID.git" style="color: #E91E63; text-decoration: none;">
    <span style="background-color: #FCE4EC; padding: 2px 6px; border-radius: 4px;"> Code</span>
  </a> -->

- <strong>United We Defend: Collaborative Membership Inference Defenses in Federated Learning.</strong><br>
   <span style="text-decoration: underline;">Li Bai</span>, Junxu Liu, Sen Zhang, Xinwei Zhang, Qingqing Ye, and Haibo Hu. USENIX Security, 2026.<br>
  <a href="https://arxiv.org/abs/2601.06866" style="color: #2196F3; text-decoration: none; font-weight: bold;">[Paper]</a>
  <a href="https://github.com/BaiLibl/CoFedMID.git" style="color: #E91E63; text-decoration: none; font-weight: bold;">[Code]</a>

- <strong>Toward Efficient Inference Attacks: Shadow Model Sharing via Mixture-of-Experts.</strong><br>
   <span style="text-decoration: underline;">Li Bai</span>, Qingqing Ye, Xinwei Zhang, Sen Zhang, Zi Liang, Jianliang Xu, Haibo Hu. 
   The Thirty-Ninth Annual Conference on Neural Information Processing Systems (NeurIPS), 2025.<br>
  <a href="https://arxiv.org/abs/2510.13451" style="color: #2196F3; text-decoration: none; font-weight: bold;">[Paper]</a>
  <a href="https://github.com/BaiLibl/ShadowPool.git" style="color: #E91E63; text-decoration: none; font-weight: bold;">[Code]</a>


- <strong>ProVFL: Property inference attacks against vertical federated learning.</strong><br>
   <span style="text-decoration: underline;">Li Bai</span>, Xinwei Zhang, Sen Zhang, Qingqing Ye,Haibo Hu. 
   IEEE Transactions Information Forensics and Security (TIFS), 2025.<br>
  <a href="https://ieeexplore.ieee.org/document/11045555" style="color: #2196F3; text-decoration: none; font-weight: bold;">[Paper]</a>
  <a href="https://github.com/BaiLibl/ProVFL.git" style="color: #E91E63; text-decoration: none; font-weight: bold;">[Code]</a>


- <strong>RMR: A relative membership risk measure for machine learning models.</strong><br>
   <span style="text-decoration: underline;">Li Bai</span>,  Haibo Hu, Qingqing Ye, Jianliang Xu, Jin Li, Chengfang Fang, Jie Shi.
   IEEE Transactions on Dependable and Secure Computing (TDSC), 2025.<br>
  <a href="https://ieeexplore.ieee.org/document/10930945" style="color: #2196F3; text-decoration: none; font-weight: bold;">[Paper]</a>
  <a href="https://github.com/BaiLibl/RelativeMI.git" style="color: #E91E63; text-decoration: none; font-weight: bold;">[Code]</a>

- <strong>Auditing MLaaS Inference Service Quality without Ground Truth via Mutual Information.</strong><br>
   Zhu Jiang, Haibo Hu, Qingqing Ye, <span style="text-decoration: underline;">Li Bai</span>.
   IEEE Transactions Information Forensics and Security (TIFS), 2025.<br>
  <a href="https://ieeexplore.ieee.org/document/11269878" style="color: #2196F3; text-decoration: none; font-weight: bold;">[Paper]</a>

- <strong>MER-Inspector: Assessing model extraction risks from an attack-agnostic perspective.</strong><br>
   Zhu Jiang, Haibo Hu, Qingqing Ye, <span style="text-decoration: underline;">Li Bai</span>.
   Proceedings of the ACM on Web Conference (WWW), 2025.<br>
  <a href="https://dl.acm.org/doi/10.1145/3696410.3714894" style="color: #2196F3; text-decoration: none; font-weight: bold;">[Paper]</a>
  <a href="https://github.com/XinweiZhang1998/MER_Inspector" style="color: #E91E63; text-decoration: none; font-weight: bold;">[Code]</a>

- <strong>A sample-level evaluation and generative framework for model inversion attacks.</strong><br>
   Haoyang Li, <span style="text-decoration: underline;">Li Bai</span>, Qingqing Ye, Haibo Hu, Yaxin Xiao, Huadi Zheng, Jianliang Xu.
   Proceedings of the Thirty-Ninth AAAI Conference on Artificial Intelligence (AAAI), 2025.<br>
  <a href="https://dl.acm.org/doi/10.1145/3696410.3714894" style="color: #2196F3; text-decoration: none; font-weight: bold;">[Paper]</a>

- <strong>Membership inference attacks and defenses in federated learning: A survey.</strong><br>
   <span style="text-decoration: underline;">Li Bai</span>, Haibo Hu, Qingqing Ye, Haoyang Li, Leixia Wang, Jianliang Xu.
   ACM Computing Surveys, 2024.<br>
  <a href="https://dl.acm.org/doi/10.1145/3704633" style="color: #2196F3; text-decoration: none; font-weight: bold;">[Paper]</a>


# 📖 Educations
- *2022.09 - now*, The Hong Kong Polytechnic University, PhD in Electronic and Information Engineering. 
- *2016.09 - 2019.06*, Chinese Academy of Sciences, Institute of Information Engineering, Master in Cyberspace Security. 
- *2012.09 - 2016.06*, Jilin University, Bachelor in Information and Network Security. 

# 🎖 Honors and Awards
- *2017.09* Outstanding Student Awards, University of Chinese Academy of Sciences. 
- *2015.12* First Prize Scholarship, Jilin University (top 5%). 
- *2015.05* Suzhou Industrial Park Scholarship, Jilin University. 
- *2014.12* China National Scholarship, Jilin University (top 2%). 
- *2013.12* China National Scholarship, Jilin University (top 2%). 

<!-- # 💬 Invited Talks
- *2021.06*, Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet. 
- *2021.03*, Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet.  \| [\[video\]](https://github.com/) -->

# 💻 Experience
- *2021.05 - 2022.08*, Research Assistant, The Hong Kong Polytechnic University, Hong Kong.
- *2019.07 - 2020.08*, Algorithm Engineer, Sogou Inc, Beijing China.

# 📋 Services
## Journal Reviewer
- IEEE Transactions on Information Forensics and Security
- IEEE Transactions on Dependable and Secure Computing 
- IEEE Transactions on Computational Social Systems

## Teaching Assistant
- Information Technology, The Hong Kong Polytechnic University, 2025
- Artificial Intelligence and Science Fiction, The Hong Kong Polytechnic University, 2024,
- Information Technology, Fundamentals of Machine Intelligence, The Hong Kong Polytechnic University, 2023
- Mobile Systems and Application Development, The Hong Kong Polytechnic University, 2022