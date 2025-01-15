---
title: Analyzing the Effects of Psychological Stress on Heart Rate Variability in High School Students
abstract: |
  This study aimed to evaluate the effects of short-term psychological stress on heart rate variability (HRV) using the root mean square of successive differences (RMSSD) parameter. A small-scale experiment was conducted with five Biomedical Engineering students (3 males, 2 females) as participants. Psychological stress was induced through a Stroop Word Color Conflict Test and a timed math test, administered in a competitive setting with an incentive for perfect accuracy. Baseline HRV measurements were recorded during a no-stress period, followed by measurements taken after the stressor. The results showed a general reduction in RMSSD values post-stress, consistent with higher stress levels. However, statistical analysis indicated no significant difference in RMSSD values before and after the stressor. These findings highlight a potential trend linking induced stress with autonomic changes but depict the need for further research with larger sample sizes to draw definitive conclusions.
---

## Introduction
High school students face frequent academic challenges, including tests, quizzes, and other high-pressure situations, which can significantly impact their stress levels. Chronic exposure to stress during adolescence, an essential period of growth and development, can lead to long-term effects like anxiety disorders, cardiovascular problems, and poor academic performance ([Stromájer _et al._, 2023](https://doi.org/10.3390/children10091548)).

Stress activates the autonomic nervous system, specifically the sympathetic branch responsible for the “fight-or-flight” response. This can lead to changes in the heart’s function, particularly in HRV [@noauthor_sympathetic_nodate]. HRV is the variation in time between consecutive heartbeats and serves as a measure of the body’s ability to adapt to stressors. HRV is regulated by the sympathetic and parasympathetic systems of the autonomic nervous system. Higher HRV indicates a balanced interaction between the sympathetic and parasympathetic branches, while lower HRV suggests heightened stress and less control of emotion regulation ([Tiwari _et al._, 2020](https://doi.org/10.2174/1573403x16999201231203854)). HRV is particularly sensitive to changes in mental and emotional states, making it a useful tool to evaluate stress response. For students, regulating stress effectively is important for long-term health. By understanding how stress influences HRV, we can develop strategies to better support high school students’ stress management and overall health. 

To better understand this relationship between stress and HRV, our study uses the Stroop Word Color Conflict Test and a timed math test to induce stress. The Stroop Test is effective for inducing cognitive stress because it creates an interference between automatic word recognition and the need to focus on the color of the words, both factors acting on you at the same time ([Scarpina _et al._, 2017](https://doi.org/10.3389/fpsyg.2017.00557)). On the other hand, timed math tests introduce pressure by imposing a time limit, which is a common stressor in academic environments. Together, these assignments cover a wide range of the stressors that students often encounter.

This study explores the relationship between academic stress and heart rate variability (HRV) in high school students. By using controlled talks that induce stress, Stroop Test, and a timed math test, this study will measure HRV before and during the tasks to assess how stress impacts our patients. It is predicted that high school students’ HRV will significantly decrease as a result of stress created by stress-inducing tasks. We hope to show that HRV can be a valid physiological indicator of stress in adolescents, offering a further understanding of the body’s ability to adjust to external pressures. These results could support the use of HRV as an effective tool for assessing stress levels and the general well-being of students. 

```{figure} images/heart_rate_variability.png
:label: figure1
:alt: An example of HRV 

Heart rate variability is the variation in time between consecutive heartbeats.
```

## Methods
A total of 5 students, 3 males and 2 females aged 16-18, were recruited from our Biomedical Engineering class using randomized selection from the class roster. Participants were screened for underlying health conditions that could interfere with testing and those who did not fit the criteria were excluded from data collection. Sociodemographic data including age and gender were collected from all participants while keeping their names anonymous. 

The study utilized a Vernier EKG sensor to capture EKG data from each participant in real time. This data would later be inputted into the Matlab program and Kubios software to obtain an RMSSD reading from each trial. 

Each participant was first asked to relax while control data was taken using the Vernier EKG sensor and electrodes. Each control reading lasted 180 seconds. After this, each participant was instructed to stay still while completing the Stroop Word Color Conflict Test in a generally quiet environment. After the two minute video finished, simple rapid-fire math problems were administered for another thirty seconds to match the time taken for obtaining control data. Over the course of the trials with stress, the sensor would take their EKG data. Finally, after all ten trials were completed, the data was inserted into MatLab and Kubios for RMSSD values. All data was collected within a one-week period. A paired t-test was used to compare the difference in RMSSD values before and after stress was applied. Our tests assumed that RMSSD values were significantly lower during stress compared to resting. Statistical significance was set at p < 0.05.

```{figure} #resting
:label: figure2

A graph of the EKG data for one of the female participants at rest over a duration of 25 seconds. 
```

```{figure} #stress
:label: figure3

A graph of the EKG data for one of the female participants under stress over a duration of 25 seconds. 
```

This flowchart depicts the simplified algorithm used by the Kubios Software to compute the RMSSD values that are used for further analysis of stress on short-term heart rate variability. For reference, this chart is specifically designed to calculate the range of RMSSD values for people aged 16-18 as the normal range varies by age.

```{mermaid}
:label: RMSSD_flowchart
:enumerated: true

flowchart TD
  A([Start]) --> B
  B[/Age/] --> C
  C[/Gender/] --> D[/EKG Data/]
  D --> E[Calculate time between each heartbeat using R-R intervals in ms.]
  E --> F[Square each interval value]
  F --> G[Take the overall mean of the intervals by adding them all together and dividing by the number of intervals]
  G --> H[Take the square root of the calculated mean]
  H --> I{Is the calculated value between 50-90 ms?}
  I --> |Yes| J[Display RMSSD is within the normal range]
  I --> |No| K[Display RMSSD is outside of the normal range]
  J --> L([End])
  K --> L([End])
```

:::{table} RMSSD, SDNN, and pNN50 values during control and stress trials for each participant
:label: tbl:values-html

<table>
   <tr>
      <th rowspan="2">Participant</th>
      <th colspan="3" align="center">Control</th>
      <th colspan="3" align="center">With Stress</th>
   </tr>
   <tr>
      <th align="center">RMSSD (ms)</th>
      <th align="center">SDNN (ms)</th>
      <th align="center">pNN50 (%)
      <th align="center">RMSSD (ms)</th>
      <th align="center">SDNN (ms)</th>
      <th align="center">pNN50 (%)
      <th>
   </tr>
   <tr>
      <td>1 (female)</td>
      <td align="center">33.4</td>
      <td align="center">38.7</td>
      <td align="center">10.94</td>
      <td align="center">23.3</td>
      <td align="center">29.3</td>
      <td align="center">3.75</td>
   </tr>
   <tr>
      <td>2 (female)</td>
      <td align="center">48.7</td>
      <td align="center">34.5</td>
      <td align="center">5.82</td>
      <td align="center">23.9</td>
      <td align="center">30.9</td>
      <td align="center">3.90</td>
   </tr>
   <tr>
      <td>3 (male)</td>
      <td align="center">48.7</td>
      <td align="center">34.8</td>
      <td align="center">5.62</td>
      <td align="center">32.6</td>
      <td align="center">40.5</td>
      <td align="center">9.68</td>
   </tr>
   <tr>
      <td>
         <bold>4 (male)</bold>
      </td>
      <td align="center">47.0</td>
      <td align="center">63.5</td>
      <td align="center">27.27</td>
      <td align="center">42.3</td>
      <td align="center">35.6</td>
      <td align="center">18.97</td>
   </tr>
   <tr>
      <td>
         <bold>5 (male)</bold>
      </td>
      <td align="center">44.5</td>
      <td align="center">30.1</td>
      <td align="center">30.19</td>
      <td align="center">45.5</td>
      <td align="center">62.5</td>
      <td align="center">17.11</td>
   </tr>
</table>

This table shows the RMSSD, SDNN, and pNN50 values taken from the Vernier EKG Sensor during control and stress trials for each participant. Our team focused on interpreting the RMSSD, or the root mean square of successive differences since this is the most accurate value to use during shorter periods of induced stress. 
:::

## Results
The data from each subject was inserted into the Kubios HRV software, where the algorithm identified an RMSSD value for each trial (refer to @RMSSD_flowchart). The analysis revealed a statistically insignificant but positive correlation between participants' reported levels of stress and their measured RMSSD, meaning that individuals experiencing higher stress levels exhibited lower HRV (p > 0.05). Furthermore, almost all participants displayed a lower RMSSD number post-stress with the exception of Participant 5, who had an increase in RMSSD of 1 ms. after stress (See @tbl:values-html). 

## Discussion
The results of this study indicate a general trend of reduced HRV, as measured by RMSSD, following exposure to psychological stressors. This finding aligns with existing literature that identifies HRV, particularly RMSSD, as a sensitive indicator of autonomic nervous system activity, where reductions typically signify heightened sympathetic activation or reduced parasympathetic influence during stress. Studies have shown that psychological stressors such as cognitive tasks and time pressure can significantly impact HRV values, particularly in small, controlled experiments like ours ([Kim _et al._, 2018](https://doi.org/10.30773/pi.2017.08.17)).

While our results demonstrated a decrease in RMSSD for most participants post-stress, the lack of statistical significance (p > 0.05) may be attributed to a small sample size (n = 5). Small sample sizes can result in greater statistical uncertainty, which makes it harder to see trends within the data. Additionally, individual variability in stress responses could have influenced the results. For instance, Participant 5 exhibited a slight increase in RMSSD post-stress, suggesting a possible coping mechanism or physiological adaptation that warrants further investigation. Previous research suggests that factors such as baseline fitness, resilience, or habituation to stress can influence HRV responses to psychological stress ([Laborde _et al._, 2017](https://doi.org/10.3389/fpsyg.2017.00213)).

The competitive environment, coupled with the Stroop and rapid-fire math tests, was designed to mimic real-world stressors, but the study's artificial setup might not fully replicate natural stress conditions. Additionally, the short duration of the stressor may have limited its impact on the autonomic nervous system compared to prolonged stress exposure, which is often studied in HRV research..

Future research should address these limitations by including a larger and more diverse sample size, as well as exploring alternative stress paradigms that more closely simulate everyday stressors. Moreover, the use of additional HRV parameters, such as the low-frequency to high-frequency (LF/HF) ratio, could provide a better understanding of the autonomic changes associated with stress.

## Conclusion
This study demonstrated a potential trend of decreased HRV, measured via RMSSD, following short-term psychological stress. However, the absence of statistically significant differences underscores the importance of larger sample sizes and more robust experimental designs to draw definitive conclusions. Despite these limitations, the findings contribute to the growing body of evidence suggesting that HRV is a promising non-invasive biomarker for assessing stress responses. Future studies should aim to refine experimental conditions and incorporate longitudinal designs to explore the relationship between stress and HRV across different populations and settings.
