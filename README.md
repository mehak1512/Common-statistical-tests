# Common-statistical-tests
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import scipy.stats as stats
Suggested code may be subject to a license |  | Ameyagidh2/projects
 one sample t-test
# Sample data
acorns_mass = [8.8, 6.6, 9.5, 11.2, 10.2, 7.4, 8.0, 9.6, 9.9, 9.0, 7.6, 7.4, 10.4, 11.1, 8.5, 10.0, 11.6, 10.7, 10.3, 7.0]
t_statistic, p_value = stats.ttest_1samp(acorns_mass, 10)
print(f"T-statistic: {t_statistic}")
print(f"P-value: {p_value}")
alpha = 0.05
if p_value < alpha:
print("We reject the null hypothesis. The average mass is significantly different from 10g.")
else:
print("We fail to reject the null hypothesis. There is no significant difference from 10g.")
T-statistic: -2.2491611580763973
P-value: 0.03655562279112415
We reject the null hypothesis. The average mass is significantly different from 10g.
 Independent two sample test
up_wind = [10.8, 10.0, 8.2, 9.9, 11.6, 10.1, 11.3, 10.3, 10.7, 9.7, 7.8, 9.6, 9.7, 11.6, 10.3, 9.8, 12.3, 11.0, 10.4, 10.4]
down_wind = [7.8, 7.5, 9.5, 11.7, 8.1, 8.8, 8.8, 7.7, 9.7, 7.0, 9.0, 9.7, 11.3, 8.7, 8.8, 10.9, 10.3, 9.6, 8.4, 6.6]
t_statistic, p_value = stats.ttest_ind(up_wind, down_wind, equal_var=True)
print(f"T-statistic: {t_statistic}")
print(f"P-value: {p_value}")
# Conclusion
if p_value < alpha:
print("We reject the null hypothesis. The acorn masses are significantly different.")
else:
print("We fail to reject the null hypothesis. There is no significant difference in the acorn masses.")
T-statistic: 3.285207388388818
P-value: 0.0021958787208365142
We reject the null hypothesis. The acorn masses are significantly different.
 Anova test
marks_A = [51, 45, 33, 45, 67]
marks_B = [23, 43, 23, 43, 45]
marks_C = [56, 76, 74, 87, 56]
f_statistic, p_value = stats.f_oneway(marks_A, marks_B, marks_C)
print(f"F-statistic: {f_statistic}")
print(f"P-value: {p_value}")
if p_value < alpha:
print("We reject the null hypothesis. There is a significant difference between the groups.")
else:
print("We fail to reject the null hypothesis. There is no significant difference between the groups.")
F-statistic: 9.747205503009463
P-value: 0.0030597541434430556
We reject the null hypothesis. There is a significant difference between the groups.
