Inputs:
```
import numpy as np
import matplotlib.pyplot as mpl
file_path = r"C:\Users\jam22\OneDrive\Desktop\heart_disease_numeric_extended.csv"
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

First Pie Chart:
```
labels=["Healthy", "Sick"]
counts=[np.sum(data[:, target] == 0), np.sum(data[:, target] == 1)]
mpl.figure()
mpl.pie(counts, labels=labels, autopct="%1.1f%%", startangle=90)
mpl.title("Heart Disease")
mpl.axis("equal")
mpl.show()
```

Second Histogram:
```
mpl.figure()
mpl.hist(data[:, age], bins=15, color="blue", edgecolor="black")
mpl.xlabel("Age")
mpl.ylabel("Patients")
mpl.title("Age")
mpl.grid(True)
mpl.show()
```

Third Histogram: 
```
healthy_chol = data[data[:, target] == 0][:, chol]
sick_chol = data[data[:, target] == 1][:, chol]
mpl.figure()
mpl.hist([healthy_chol, sick_chol], bins=40, stacked=True, label=["Healthy", "Sick"], color=["green", "red"])
mpl.title("Cholesterol Level")
mpl.xlabel("Serum Cholesterol")
mpl.ylabel("Patients")
mpl.legend()
mpl.grid(True)
mpl.show()
```

Fourth Scatter:
```
sick = data[data[:, target] == 1]
sizes = sick[:, bmi] * 1  
scatter = mpl.scatter(sick[:, trestbps], sick[:, thalach], c=sick[:, age])
mpl.colorbar(scatter, label="Age")
mpl.xlabel("Resting Blood Pressure")
mpl.ylabel("Max Heart Rate")
mpl.title("Blood Pressure and Heart Rate 'Sick Patients'")
mpl.grid(True)
mpl.show()
```

Fifth Bar Chart:
```
bins = [30, 40, 50, 60, 70, 80]
labels = ["30–39", "40–49", "50–59", "60–69", "70–79"]
avg_thalach = []
for i in range(len(bins) - 1):
 age_mask = (data[:, age] >= bins[i]) & (data[:, age] < bins[i + 1])
 avg = np.mean(data[age_mask, thalach])
 avg_thalach.append(avg)
mpl.figure()
mpl.bar(labels, avg_thalach, color="purple", edgecolor="black")
mpl.xlabel("Age Group")
mpl.ylabel("Average Max Heart Rate")
mpl.title("Average Max Heart Rate by Age Group")
mpl.grid(axis="y")
mpl.show()
```

Whole Code
```
import numpy as np
import matplotlib.pyplot as mpl
file_path = r"C:\Users\jam22\OneDrive\Desktop\heart_disease_numeric_extended.csv"
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
mpl.figure()
mpl.pie(counts, labels=labels, autopct="%1.1f%%", startangle=90)
mpl.title("Heart Disease")
mpl.axis("equal")
mpl.show()

mpl.figure()
mpl.hist(data[:, age], bins=15, color="blue", edgecolor="black")
mpl.xlabel("Age")
mpl.ylabel("Patients")
mpl.title("Age")
mpl.grid(True)
mpl.show()

healthy_chol = data[data[:, target] == 0][:, chol]
sick_chol = data[data[:, target] == 1][:, chol]
mpl.figure()
mpl.hist([healthy_chol, sick_chol], bins=40, stacked=True, label=["Healthy", "Sick"], color=["green", "red"])
mpl.title("Cholesterol Level")
mpl.xlabel("Serum Cholesterol")
mpl.ylabel("Patients")
mpl.legend()
mpl.grid(True)
mpl.show()

sick = data[data[:, target] == 1]
sizes = sick[:, bmi] * 1  
scatter = mpl.scatter(sick[:, trestbps], sick[:, thalach], c=sick[:, age])
mpl.colorbar(scatter, label="Age")
mpl.xlabel("Resting Blood Pressure")
mpl.ylabel("Max Heart Rate")
mpl.title("Blood Pressure and Heart Rate 'Sick Patients'")
mpl.grid(True)
mpl.show()

bins = [30, 40, 50, 60, 70, 80]
labels = ["30–39", "40–49", "50–59", "60–69", "70–79"]
avg_thalach = []
for i in range(len(bins) - 1):
 age_mask = (data[:, age] >= bins[i]) & (data[:, age] < bins[i + 1])
 avg = np.mean(data[age_mask, thalach])
 avg_thalach.append(avg)
mpl.figure()
mpl.bar(labels, avg_thalach, color="purple", edgecolor="black")
mpl.xlabel("Age Group")
mpl.ylabel("Average Max Heart Rate")
mpl.title("Average Max Heart Rate by Age Group")
mpl.grid(axis="y")
mpl.show()
```
