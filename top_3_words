def top_3_words(text):
    import re, string
    arr = re.findall("[\w']+", text)
    index = 0
    while index<len(arr):
        l=arr[index]
        if any(j=='_' for j in l):
            add=l.split('_')
            arr.pop(index)
            index-=1
            for k in add:
                if k!=('' and '_'):
                    arr.append(k)
        index+=1
    for i in arr:
        if all(j in string.punctuation for j in i) or i=='':
            arr.remove(i)
    words = list()
    cnt = list()
    for i in arr:
        i=i.lower()
        if i in words:
            cnt[words.index(i)] += 1
        else:
            words.append(i)
            cnt.append(1)
    out=[]
    i=0
    while i<3:
        if words:
            ind = cnt.index(max(cnt))
            out.append(words[ind])
            words.pop(ind)
            cnt.pop(ind)
        i+=1
    return out
