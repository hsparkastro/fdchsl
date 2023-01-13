---
layout: page
title: Aviation Safety Management with Big Data Platform Implementation
description: Data-driven methods to identify, detect, and predict safety events in air traffic control, with a focus on Area Navigation (RNAV) airspace.
img: assets/projects/atm/total_traj.png
bibliography: assets/projects/atm/hyunsang_bib.bib
importance: 1
category: work
---
<script src="{{ '/assets/js/distillpub/template.v2.js' | relative_url }}"></script>
<script src="{{ '/assets/js/distillpub/transforms.v2.js' | relative_url }}"></script>
<script src="{{ '/assets/js/distillpub/overrides.js' | relative_url }}"></script>

**Safety events** in aviation are events that compromise the safety of aircraft operations. Since safety events (especially potential unknown safety events) are unlabeled, we focus on identifying and detecting **anomalies** – statistically significant events that deviate from the majority – as they are candidates for safety events. We also focus on detecting **precursors**, which are events that precede a known safety event. **Data-driven methods** are suited for these problems since they can infer information from historical data to aid the identification and prediction of safety events, as opposed to physics-based methods which can only rely on the recorded information of a particular flight and its dynamics.

**Area Navigation (RNAV)** is a method of navigation that permits an aircraft to fly on any desired path within the coverage of navigation aids. RNAV allows ATCs to coordinate aircraft within the RNAV airspace to improve efficiency, by using direct paths whenever possible to save time/fuel and rearranging the order of arriving flights to minimize delays. However, this flexibility also creates complex trajectory behaviors such that existing tools designed to detect and predict anomalies fail to perform well. 
<div class="container">
    <div class="row-sm"><div class="col">
            {% include figure.html path="assets/projects/atm/total_traj.png" title="example image" class="img-fluid" caption="Example of an RNAV terminal airspace: Arrival (left) and departure (right) trajectories around Incheon International Airport (1 month). " %}
    </div></div>
</div>
We tackle the problem of effectively modeling the behavior of trajectories in a complex and structured terminal airspace with RNAV. In previous research, trajectories are clustered to produce groups of trajectories (or patterns) with similar behavior that are distinct from other patterns and study each cluster separately. However, well-known clustering algorithms (DBSCAN, K-means, etc) are not suitable for RNAV terminal airspace, as it produces clusters that have wide inter-cluster variance and is not informative to data-driven algorithms. To tackle this problem, we developed a trajectory pattern identification framework using hierarchical agglomerative clustering and Dynamic Time Warping (DTW) that can produce patterns with small variance.

With the identified cluster as labels, we trained a Recurrent Neural Network-based model that can classify trajectory patterns online and compute the probabilities of the partial trajectory belonging to the identified patterns. By combining the trajectory pattern identification and real-time classification frameworks, historical air surveillance data recorded in the RNAV terminal airspace can be better studied and therefore data-driven air traffic assistant tools can be better developed and implemented. 

To incorporate the historical behaviors of aircraft with the current flight mode or dynamics, we developed a framework for more accurate trajectory prediction in terminal airspace by combining machine learning and estimation techniques. This framework consists of three steps:
- Data preparation is first performed by using data cleaning and trajectory pattern identification
- A machine-learning-based trajectory prediction model is trained with historical data to generate the probability distribution of an incoming flight’s future states
- The aircraft’s dynamics is modeled as a stochastic linear hybrid system, i.e., Residual-Mean Interacting Multiple Model (RM-IMM), to estimate the future states of the aircraft using the data-driven prediction as the pseudo-measurement
The proposed framework improves the prediction accuracy by using RM-IMM to correct the data-driven prediction to follow the aircraft’s dynamics.

#### Graduate Students
- Kwangyeon Kim
- Hong-Cheol Choi
- Chuhao Deng
- Hyunsang Park

#### Project Information 
Aviation Safety Management with Big Data Platform Implementation (Grant 21BDAS-B158275-02)
- Period: 2020.04 - 2023.12
- Sponsors and Collaborators
<div class="container-sm">
  <div class="row row-cols-3 justify-content-md-center align-items-center">
    <div class="col-3">
      {% include figure.html path="assets/projects/atm/molit.jpg" class="img-fluid" %}
      {% include figure.html path="assets/projects/atm/kaia.png" class="img-fluid" %}
    </div>
    <div class="col-3">
      {% include figure.html path="assets/projects/atm/inha_cropped.jpg" class="img-fluid" %}
      {% include figure.html path="assets/projects/atm/clunix.png" class="img-fluid" %}
    </div>
    <div class="col-4">
      {% include figure.html path="assets/projects/atm/aaici_cropped.jpg" class="img-fluid" %}
      {% include figure.html path="assets/projects/atm/etri_cropped.jpg" class="img-fluid" %}
      {% include figure.html path="assets/projects/atm/kiast_cropped.jpg" class="img-fluid" %}
      {% include figure.html path="assets/projects/atm/neighborsystem_cropped.png" class="img-fluid" %}
    </div>
  </div>
</div>

#### Related Publications 
{% reference park2021adaptive %}