```python
import pandas as pd


def createDataframe(student_data: List[List[int]]) -> pd.DataFrame:
	return pd.DataFrame(student_data, columns=["student_id","age"])


def getDataframeSize(players: pd.DataFrame) -> List[int]:
    return list(players.shape)


def selectFirstRows(employees: pd.DataFrame) -> pd.DataFrame:
    return employees.head(3)


def selectData(students: pd.DataFrame) -> pd.DataFrame:
    return students.loc[students['student_id'] == 101, ['name', 'age']]


def createBonusColumn(employees: pd.DataFrame) -> pd.DataFrame:
    employees['bonus'] = employees['salary'] * 2
    return employees


def dropDuplicateEmails(customers: pd.DataFrame) -> pd.DataFrame:
    return customers.drop_duplicates('email')
    

def dropMissingData(students: pd.DataFrame) -> pd.DataFrame:
    return students.dropna(subset=['name'])


def modifySalaryColumn(employees: pd.DataFrame) -> pd.DataFrame:
    employees['salary'] = employees['salary'] * 2
    return employees
    

def renameColumns(students: pd.DataFrame) -> pd.DataFrame:
    return students.rename(columns={'id':'student_id','first':'first_name','last':'last_name','age':'age_in_years'})


def changeDatatype(students: pd.DataFrame) -> pd.DataFrame:
    students['grade'] = students['grade'].astype(int)
    return students


def fillMissingValues(products: pd.DataFrame) -> pd.DataFrame:
    products['quantity'] = products['quantity'].fillna(0)
    return products


def concatenateTables(df1: pd.DataFrame, df2: pd.DataFrame) -> pd.DataFrame:
    return pd.concat([df1, df2])


def pivotTable(weather: pd.DataFrame) -> pd.DataFrame:
    return weather.pivot(columns='city', index='month', values='temperature')
'''
**Input:**
+--------------+----------+-------------+
| city         | month    | temperature |
+--------------+----------+-------------+
| Jacksonville | January  | 13          |
| Jacksonville | February | 23          |
| Jacksonville | March    | 38          |
| Jacksonville | April    | 5           |
| Jacksonville | May      | 34          |
| ElPaso       | January  | 20          |
| ElPaso       | February | 6           |
| ElPaso       | March    | 26          |
| ElPaso       | April    | 2           |
| ElPaso       | May      | 43          |
+--------------+----------+-------------+
**Output:**
 +----------+--------+--------------+ 
 | month    | ElPaso | Jacksonville | 
 +----------+--------+--------------+ 
 | April    | 2      | 5            | 
 | February | 6      | 23           | 
 | January  | 20     | 13           | 
 | March    | 26     | 38           | 
 | May      | 43     | 34           | 
 +----------+--------+--------------+
'''


def meltTable(report: pd.DataFrame) -> pd.DataFrame:
    return report.melt(id_vars=['product'], var_name='quarter',value_name='sales')
    
'''
**Input:**
+-------------+-----------+-----------+-----------+-----------+
| product     | quarter_1 | quarter_2 | quarter_3 | quarter_4 |
+-------------+-----------+-----------+-----------+-----------+
| Umbrella    | 417       | 224       | 379       | 611       |
| SleepingBag | 800       | 936       | 93        | 875       |
+-------------+-----------+-----------+-----------+-----------+
**Output:**
+-------------+-----------+-------+
| product     | quarter   | sales |
+-------------+-----------+-------+
| Umbrella    | quarter_1 | 417   |
| SleepingBag | quarter_1 | 800   |
| Umbrella    | quarter_2 | 224   |
| SleepingBag | quarter_2 | 936   |
| Umbrella    | quarter_3 | 379   |
| SleepingBag | quarter_3 | 93    |
| Umbrella    | quarter_4 | 611   |
| SleepingBag | quarter_4 | 875   |
+-------------+-----------+-------+
'''


def findHeavyAnimals(animals: pd.DataFrame) -> pd.DataFrame:
    return animals[animals['weight'] > 100].sort_values(['weight'], ascending=False)[['name']]
```