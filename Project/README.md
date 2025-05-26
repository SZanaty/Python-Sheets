# Code Prensibles
##Inputs
```
import numpy as np
import matplotlib.pyplot as plt
file_path = r'C:\Users\jam22\OneDrive\Desktop\heart_disease_numeric_extended.csv'
data = np.genfromtxt(file_path, delimiter=',', skip_header=1)
data = data[~np.isnan(data).any(axis=1)]
age=0
sex=1
trestbps = 2
chol = 3
thalach = 4
oldpeak = 5
ca = 6
blood_glucose = 7
spo2 = 8
bmi = 9
target = 10
```
##First Chart
```
labels=["Healthy", "Sick"]
counts=[np.sum(data[:, target] == 0), np.sum(data[:, target] == 1)]
plt.figure()
plt.pie(counts, labels=labels, autopct="%1.1f%%", startangle=90)
plt.title("Heart Disease")
plt.axis("equal")
plt.show()
```

plt.figure()
plt.hist(data[:, age], bins=10, color="blue", edgecolor="black")
plt.xlabel("Age")
plt.ylabel("Patients")
plt.title("Age")
plt.grid(True)
plt.show()

healthy_chol = data[data[:, target] == 0][:, chol]
sick_chol = data[data[:, target] == 1][:, chol]
plt.figure()
plt.hist([healthy_chol, sick_chol], bins=20, stacked=True, label=["Healthy", "Sick"], color=["green", "red"])
plt.title("Cholesterol Level")
plt.xlabel("Serum Cholesterol")
plt.ylabel("Patients")
plt.legend()
plt.grid(True)
plt.show()

sick = data[data[:, target] == 1]
sizes = sick[:, bmi] * 1  
scatter = plt.scatter(sick[:, trestbps], sick[:, thalach], c=sick[:, age])
plt.colorbar(scatter, label="Age")
plt.xlabel("Resting Blood Pressure")
plt.ylabel("Max Heart Rate")
plt.title("Blood Pressure and Heart Rate 'Sick Patients'")
plt.grid(True)
plt.show()

bins = [30, 40, 50, 60, 70, 80]
labels = ["30–39", "40–49", "50–59", "60–69", "70–79"]
avg_thalach = []
for i in range(len(bins) - 1):
 age_mask = (data[:, age] >= bins[i]) & (data[:, age] < bins[i + 1])
 avg = np.mean(data[age_mask, thalach])
 avg_thalach.append(avg)
plt.figure()
plt.bar(labels, avg_thalach, color="purple", edgecolor="black")
plt.xlabel("Age Group")
plt.ylabel("Average Max Heart Rate (bpm)")
plt.title("Average Max Heart Rate by Age Group")
plt.grid(axis="y")
plt.show()


Whole Code
```
import numpy as np
import matplotlib.pyplot as plt
file_path = r'C:\Users\jam22\OneDrive\Desktop\heart_disease_numeric_extended.csv'
data = np.genfromtxt(file_path, delimiter=',', skip_header=1)
data = data[~np.isnan(data).any(axis=1)]
age=0
sex=1
trestbps = 2
chol = 3
thalach = 4
oldpeak = 5
ca = 6
blood_glucose = 7
spo2 = 8
bmi = 9
target = 10

labels=["Healthy", "Sick"]
counts=[np.sum(data[:, target] == 0), np.sum(data[:, target] == 1)]
plt.figure()
plt.pie(counts, labels=labels, autopct="%1.1f%%", startangle=90)
plt.title("Heart Disease")
plt.axis("equal")
plt.show()

plt.figure()
plt.hist(data[:, age], bins=10, color="blue", edgecolor="black")
plt.xlabel("Age")
plt.ylabel("Patients")
plt.title("Age")
plt.grid(True)
plt.show()

healthy_chol = data[data[:, target] == 0][:, chol]
sick_chol = data[data[:, target] == 1][:, chol]
plt.figure()
plt.hist([healthy_chol, sick_chol], bins=20, stacked=True, label=["Healthy", "Sick"], color=["green", "red"])
plt.title("Cholesterol Level")
plt.xlabel("Serum Cholesterol")
plt.ylabel("Patients")
plt.legend()
plt.grid(True)
plt.show()

sick = data[data[:, target] == 1]
sizes = sick[:, bmi] * 1  
scatter = plt.scatter(sick[:, trestbps], sick[:, thalach], c=sick[:, age])
plt.colorbar(scatter, label="Age")
plt.xlabel("Resting Blood Pressure")
plt.ylabel("Max Heart Rate")
plt.title("Blood Pressure and Heart Rate 'Sick Patients'")
plt.grid(True)
plt.show()

bins = [30, 40, 50, 60, 70, 80]
labels = ["30–39", "40–49", "50–59", "60–69", "70–79"]
avg_thalach = []
for i in range(len(bins) - 1):
 age_mask = (data[:, age] >= bins[i]) & (data[:, age] < bins[i + 1])
 avg = np.mean(data[age_mask, thalach])
 avg_thalach.append(avg)
plt.figure()
plt.bar(labels, avg_thalach, color="purple", edgecolor="black")
plt.xlabel("Age Group")
plt.ylabel("Average Max Heart Rate (bpm)")
plt.title("Average Max Heart Rate by Age Group")
plt.grid(axis="y")
plt.show()
```
