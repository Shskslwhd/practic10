# practic10
#1
import sys
import matplotlib
matplotlib.use('Agg')

import pandas as pd
import matplotlib.pyplot as plt
from scipy import stats

full_health_data = pd.read_csv("data.csv", header=0, sep=",")

x = full_health_data["x2"]
y = full_health_data["x3"]

slope, intercept, r, p, std_err = stats.linregress(x, y)

def myfunc(x):
 return slope * x + intercept

mymodel = list(map(myfunc, x))

plt.scatter(x, y)
plt.plot(x, mymodel)
plt.ylim(ymin=0, ymax=2)
plt.xlim(xmin=0, xmax=2)
plt.xlabel("x2")
plt.ylabel ("x3")
plt.show()


plt.savefig(sys.stdout.buffer)
sys.stdout.flush()

#2
import numpy as np

x = np.arange(15, dtype=np.int64).reshape(3, 5)

print(x)
#3
import pandas as pd

d={'Men': ['Ansagan','Allabergen','Bakhtiar','Esbol','Adlet','Adilet','Aibek','Mukhtar','Erzhan','Aidos','Muhammed'],
'Women': ['Aikerim','Ayana','Diana','Madina','Aruzhan','Gulnur','Moldir','Aknur','Mansura','Tamila','Zhannur']}

df = pd.DataFrame(data=d)

print(df)

#4
import pandas as pd
import numpy as np
a=[172,150,156,136,148,170,180,189,152,156,147,196,120,130,146,178,187,195,165,135]
print ('Ең ұзын адам бой өлшемі:', max(a))
print ('Ең қысқа адам бой өлшемі:', min(a))
print ('Бой өлшемдерінің орташа мәні:',np.mean(a))
