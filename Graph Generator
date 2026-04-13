import csv
import numpy as np
import matplotlib.pyplot as plt

x =list(range(556))

print("Welcome to Our Graph Generator.\n"
      "Before processing, please make sure that you have the excel file in the same folder as this generator.")

file = input("Let us know the name of the file to graph: ")
# Open the file
#with open('3F_S1-TR-020226093854.csv', mode='r', newline='') as f:
with open(file, mode='r', newline='') as f:
    # Create a reader object
    reader = csv.reader(f)
    # Convert the entire CSV into a list
    data = list(reader)

exceptTitle = data[3:]


# Step 2: Convert the remaining list to a NumPy array
npData = np.array(exceptTitle, dtype = float)

# Step 3: Use NumPy's [rows, columns] slicing to skip the first column (Index 0)
# This says: "Keep all rows (:), start from column 1 until the end (1:)"
finalData = npData[:, 8:]


sensors = [list(finalData[:,i]) for i in range(32)] # 모든 센서 결과 (s1-s32)를 sensors 이라는 list 에 저장

for j in range(32):                                 #s1, s2, s3.... s32 소환
    print(f"SENSOR {j+1}")
    current_sensor = sensors[j]                           # plotting
    plt.subplot(4, 8, j + 1)
    plt.subplots_adjust(left=0.1, right=0.9, top=0.9, bottom=0.1, wspace=0.6, hspace=0.6)
    plt.title(f'S{j+1}', fontsize= 8)
    plt.plot(x,current_sensor, color ='steelblue', ms = 0.3)
plt.suptitle("E-nose Result Analysis")
plt.show()
