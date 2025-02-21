# pandas
import pandas as pd

data=pd.read_excel(r"C:\Users\panchal_____om\Downloads\espn cric score (1).xlsx",header=3)



data

data["SR"].unique

data[data["SR"]=="-"].index

data.drop(data[data["SR"]=="-"].index,inplace=True)

data["SR"].unique

data.reset_index(drop="index",inplace=True)

data

data.select_dtypes(include="object").columns

data[['Mat','HS','BF','4s','6s']]=data[['Mat','HS','BF','4s','6s']].replace("[*+]",'',regex=True).astype(int)

data[["SR"]]=data[["SR"]].replace("[*+]",'',regex=True).astype(float)

data.info()

data["Country"]=data["Player"].str.split(" ").str[-1].replace("[()]","",regex=True)

data["Player"]=data["Player"].str.split("(").str[0]

data.drop(["Team"],axis=1,inplace=True)

data["start"]=data["Span"].str.split("-").str[0].astype(int)
data["End"]=data["Span"].str.split("-").str[-1].astype(int)

data

data.info()

data.drop("Span",axis=1,inplace=True)

data



data.to_csv(r"C:\Users\panchal_____om\Downloads\pandas_cricket_score.csv",index=False)



