---
layout: archive
title: ""
permalink: /sitemap/
author_profile: true
---
李作杰
======
* 年龄：28​
* 籍贯: 山东泰安
* 政治面貌：中共党员
* 工作地点：北京师范大学化学学院（放射性药物教育部重点实验室）＆物理与天文学院（放射线束教育部重点实验室），博士后

研究方向
======
* 计算机辅助药物设计
  * 同源建模
  * 结构设计优化
  * 分子动力学模拟
* 抗肿瘤药物
  * 靶点筛选及分子设计合成
  * 生物活性测试及作用机制研究
  * 药物制剂
* 放射性药物
  * PET
  * SPECT

教育经历
======
* 2015.09-2019.06   聊城大学       生物工程            工学学士
* 2019.09-2022.06   聊城大学       生物化学与分子工程   理学硕士
* 2022.09-2025.06   北京师范大学   药物化学与分子工程   理学博士
* 2025.07-          北京师范大学   物理学               博士后

工作经历
======
* 2017.10-2017.11    华润雪花       见习
* 2018.12-2019.01    恒瑞医药       见习
* 2019.02-2019.07    新和成药业     见习
  
已发表论文 (独立一作)
======
* J Med Chem,  2025, 68(21): 23620-23631.
* J Med Chem,  2024, 67(24): 21644-21670.
* J Med Chem,  2024, 67(23): 21617-21628.
* J Med Chem,  2021, 64(24): 17920-17935.
* Mol Pharm,  2024, 21(10): 5305-5314.
* Dalton Trans,  2022, 51(33): 12604-12619.
* Dalton Trans, 2021, 50(1):362-375.
* Mini Rew Med Chem , 2025, 25(17), 1321-1333.
* Monatsh Chem,  2020, 151(3): 353-367.
* J Liaocheng Univ , 2020, 33(5): 97-103. 

奖项荣誉
======
* 2020.05 聊城大学优秀学生干部
* 2022.06 聊城大学研究生优秀成果一等奖
* 2023.05 北京师范大学第四届研究生学术会议墙报一等奖
* 2025.04 第十七届全国放射性药物与标记化合物学术交流会优秀壁报
* 2025.05 原子高科博士生奖学金



-----------------------------------------------------------------

<h2>Posts</h2>
{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %}

{% capture written_label %}'None'{% endcapture %}

{% for collection in site.collections %}
{% unless collection.output == false or collection.label == "posts" %}
  {% capture label %}{{ collection.label }}{% endcapture %}
  {% if label != written_label %}
  <h2>{{ label }}</h2>
  {% capture written_label %}{{ label }}{% endcapture %}
  {% endif %}
{% endunless %}
{% for post in collection.docs %}
  {% unless collection.output == false or collection.label == "posts" %}
  {% include archive-single.html %}
  {% endunless %}
{% endfor %}
{% endfor %}







[更多详情见个人主页](https://zuojie-li.github.io/)
