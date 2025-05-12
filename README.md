### jupyter에서 변환된 parquet 파일 읽기
### pandas 라이브러리 사용
```
import pandas as pd
import sys

a = sys.argv[1]

def cnt(a):
    df = pd.read_parquet("~/tmp/history.parquet")
    fdf = df[df['cmd'].str.contains(a)]
    cnt = fdf['cnt'].sum()
    return(cnt)

def read_parquet(path="~/tmp/history.parquet"):
    df = pd.read_parquet("~/tmp/history.parquet")
    return df

def query():
    i = cnt(a)
    print(f'질의:{a}에 대한 결과는 {i}입니다')
    print("질의:%s에 대한 결과는 %s입니다" % (a,i))
    print("질의:%10s에 대한 결과는 %d입니다" % (a,i))
```
<img src="https://github.com/user-attachments/assets/c49b599a-8e09-496e-a92d-a36d02a59fbb" width="600">
