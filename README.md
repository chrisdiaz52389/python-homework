# python-homework
--------------------
import pandas as pd
import pathlib as path
import csv
file_path = Path("budget_data.csv")
csvpath = Path("budget_data.csv")
budget_data = pd.read_csv(csvpath)

-------------------------
file_to_load = Path("budget_data.csv")
file_to_output = Path("analysis/budget_analysis.txt")

------------------------
total_months = 0
months_of_change = []
net_change_list = []
greatest_increase = ["", 0]
greatest_decrease = ["", 999999999999999999]
total_net = 0

-----------------------------
df = pd.read_csv(file_to_load)

df['shifter'] = df['Profit/Losses'].shift(1)

df['diff'] = df['Profit/Losses'] - df['shifter']

df1 = df.sort_values(by=['diff'], ascending=False)

print(df1)

--------------------------------
##ANSWER
  Date  Profit/Losses    shifter       diff
  
25  Feb-2012        1170593  -755566.0  1926159.0

47  Dec-2013        1150461  -687986.0  1838447.0

79  Aug-2016         569899 -1163797.0  1733696.0

32  Sep-2012         475062 -1022534.0  1497596.0

45  Oct-2013         268997 -1196225.0  1465222.0
..       ...            ...        ...        ...
31  Aug-2012       -1022534   506702.0 -1529236.0

73  Feb-2016       -1100387   650000.0 -1750387.0

78  Jul-2016       -1163797   712961.0 -1876758.0

44  Sep-2013       -1196225   999942.0 -2196167.0

0   Jan-2010         867884        NaN        NaN
