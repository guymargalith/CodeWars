def simplify(poly):
    arr = list(poly)
    opr = []
    vars = []
    vartemp=[]
    optemp = []
    if arr[0] != '-' and arr[0]!='+' and not arr[0].isdigit():
        opr.append('+')
    for i in range(0,len(arr)):
        if arr[i] !='+' and arr[i] != '-' and not arr[i].isdigit():
            vartemp.append(arr[i]) 
            if len(optemp)!=0:
                opr.append(''.join(optemp))
                optemp =[]
        else:
            optemp.append(arr[i])
            if len(vartemp)!=0:
                vartemp.sort()
                vars.append(''.join(vartemp))
                vartemp =[]
    vartemp.sort()
    vars.append(''.join(vartemp))
    i=0
    varout=[]
    opout=[]
    while i<len(vars):
        if opr[i]=='+':
            opuse = 1
        elif opr[i]=='-':
            opuse = -1
        else:
            opuse = int(opr[i])
        if vars[i] in varout:
            opout[varout.index(vars[i])]= opout[varout.index(vars[i])]+opuse
        else:
            varout.append(vars[i])
            opout.append(opuse)
        i +=1
    matrix = [[varout[x],opout[x]] for x in range(0,len(varout))]
    matrix.sort()
    matrix = sorted(matrix, key=lambda x: (len(x[0])))
    strout=''
    for x,y in matrix:
        if y==0:
            continue
        if not strout and y>0:
            if y==1:
                strout=x
            else:
                strout=str(y)+x
            continue
        if y>0:
            if y==1:
                strout = strout+'+'+x
            else:
                strout = strout+'+'+str(y)+x
        else:
            if y==-1:
                strout = strout+'-'+x
            else:
                strout = strout+str(y)+x
    return strout
