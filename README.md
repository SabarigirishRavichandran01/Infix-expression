x=input()#2+3-4*6/1  #3+2*6-6/2
s=[]
o=[]
c=[]
def press(v):
    if (v=='+' or v=='-'):
        return 1
    else:
        return 2
for i in range(len(x)):
    if(x[i]>='0' and x[i]<='9'):
        s.append(int(x[i]))
        #print(s)
    else:
        v=press(x[i])
        if len(c)==0 or (c[len(c)-1]<=v):
            o.append(x[i])
            c.append(v)
        else:
            v1=s.pop()
            v2=s.pop()
            w=o.pop()
            #print(v2,w,v1)
            if(w=='+'):
                s.append(v2+v1)
            elif(w=='-'):
                s.append(v2-v1)
            elif(w=='*'):
                s.append(v2*v1)
            elif(w=='/'):
                s.append(v2//v1)
            o.append(x[i])
            c.append(v)
            #print("else",s)
        #print("num",s)
        #print("opern",o)
while len(o)!=0:
    v1=s.pop()
    v2=s.pop()
    w=o.pop()
    #print(v2,w,v1)
    if(w=='+'):
        s.append(v2+v1)
    elif(w=='-'):
        s.append(v2-v1)
    elif(w=='*'):
        s.append(v2*v1)
    elif(w=='/'):
        s.append(v2//v1)
print(s.pop())
