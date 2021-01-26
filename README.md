import datetime 
import calendar 
  
def findDay(date): 
    born = datetime.datetime.strptime(date, '%d %m %Y').weekday() 
    return (calendar.day_name[born]) 

def solution(D):
    r=dict()
    for i in D.keys():
        temp1=i
        i=i.split('-')
        temp=i[2]+' '+i[1]+' '+i[0]
        temp=findDay(temp)
        
        r[temp]=r.get(temp,0)+D.get(temp1)
        
    
    print(r)



D={'2020-01-01':4, '2020-01-02':4, '2020-01-03':6, '2020-01-04':8, '2020-01-05':2, '2020-01-06':-6, '2020-01-07':2, '2020-01-08':-2}
res=solution(D)
