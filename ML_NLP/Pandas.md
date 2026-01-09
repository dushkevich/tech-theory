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
    

```