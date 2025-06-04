---
layout: archive
# title: #""
permalink: /
author_profile: true
redirect_from:
  - /resume
---
<!-- ---
permalink: /
title: "Xiao Cai"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
--- -->
{% include base_path %}

<!-- 教育经历卡片 -->
<div class="card">
  <h2>Education</h2>
  <ul>
    <li>Ph.D. in Systems Engineering, City University of Hong Kong, 2026 (expected)</li>
    <li>M.E. in Mechanical Engineering, Xi'an Jiaotong University, 2022</li>
    <li>B.E. in Mechanical Engineering, Xi'an Jiaotong University, 2019</li>
  </ul>
</div>

<!-- Publications卡片 -->
<div class="card">
  <h2>Publications</h2>
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
</div>

<!-- 研究经历卡片 -->
<div class="card">
  <h2>Research Experience</h2>
  <ul>
    <li>Outlier detection and data recovery in the Drivetrain Diagnostics Simulator
      <ul>
        <li>Improve the local-outlier-factor-based and tacker-decomposition-based methods</li>
        <li>Clean abnormal data and recover missing data for condition-monitoring data quality assurance</li>
      </ul>
    </li>
    <li>Cutting tool remaining useful life prediction
      <ul>
        <li>Propose an optimal sensor group selection algorithm</li>
        <li>Integrate online monitoring multi-sensor signals and offline state observations to predict RUL</li>
      </ul>
    </li>
    <li>Wind turbine condition monitoring and remaining useful life prediction
      <ul>
        <li>Established a model-data-fusion remaining useful life prediction method with multi-sensor fusion</li>
        <li>Monitored 1000 wind turbines and accurately predicted 3 wind turbines failure</li>
      </ul>
    </li>
    <li>Software development for axle fault diagnosis and remaining useful life prediction
      <ul>
        <li>Established a self-data-driven remaining useful life prediction method for axle gears and bearings</li>
        <li>Responsible for algorithm optimization and software development</li>
      </ul>
    </li>
    <li>Condition monitoring and fault diagnosis algorithm development for gearbox bench test
      <ul>
        <li>Responsible for data decryption and analysis of a closed analyzer</li>
        <li>Enabled the secondary development of the closed analyzer</li>
      </ul>
    </li>
  </ul>
</div>

<!-- 荣誉奖项卡片 -->
<div class="card">
  <h2>Honors & Awards</h2>
  <ul>
    <li>Contest
      <ul>
        <li>2017 China Undergraduate Mathematical Contest in Modeling: First-grade award in Shaanxi venue</li>
        <li>2020 China Postgraduate Mathematical Contest in Modeling: Second-grade award nationally</li>
      </ul>
    </li>
    <li>Scholarship
      <ul>
        <li>National Scholarship (Top 0.2%)</li>
        <li>National Encouragement Scholarship</li>
        <li>Special Prize Scholarship (2 times)</li>
        <li>Outstanding Freshman Scholarship (Grade 1)</li>
        <li>The SiYuan Scholarship (placed first)</li>
        <li>SKF Scholarship</li>
      </ul>
    </li>
    <li>Award
      <ul>
        <li>Excellent Graduation Thesis (Top 1%)</li>
        <li>Excellent Student Award (2 times)</li>
        <li>Excellent Student Cadre Award</li>
        <li>Outstanding Graduates Award</li>
        <li>Excellent Postgraduate Award</li>
        <li>Excellent Postgraduate Cadre Award</li>
        <li>Outstanding Postgraduates Award</li>
        <li>Advanced Class Award (as monitor)</li>
      </ul>
    </li>
  </ul>
</div>

<!-- 技能卡片 -->
<div class="card">
  <h2>Skills</h2>
  <ul>
    <li>Language
      <ul>
        <li>IELTS: 7.0 (Listening: 6.5 / Reading: 7.5 / Writing: 7.0 / Speaking: 6.0)</li>
        <li>College English Test Band 4 (CET-4) Certificate</li>
        <li>College English Test Band 6 (CET-6) Certificate</li>
      </ul>
    </li>
    <li>Software
      <ul>
        <li>MATLAB, Python, C, Markdown</li>
        <li>Autodesk CAD, Autodesk Inventor, SolidWorks</li>
        <li>Arduino IDE</li>
        <li>Word, Excel, PowerPoint, Visio</li>
      </ul>
    </li>
  </ul>
</div>

<!-- 其他内容可继续添加 -->
<!-- Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul> -->
  
<!-- Service and leadership
======
* Currently signed in to 43 different slack teams -->
