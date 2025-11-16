## Hidden Test Cases

### Test Case 1
**Input**
```
>a>b>c
```
**Expected Output**
```
>a>b>c
```

---

### Test Case 2
**Input**
```
>a>@>b
```
**Expected Output**
```
>a>b
```

---

### Test Case 3
**Input**
```
>a>@@>b
```
**Expected Output**
```
>b
```

---

### Test Case 4
**Input**
```
>@>@@>a>b
```
**Expected Output**
```
>a>b
```

---

### Test Case 5
**Input**
```
>a>b>@@
```
**Expected Output**
```
>a
```

---

### Test Case 6
**Input**
```
>a>b>@@>c>d
```
**Expected Output**
```
>a>c>d
```

---

### Test Case 7
**Input**
```
>a>@@>@@>b>@@>c
```
**Expected Output**
```
>c
```

---

### Test Case 8
**Input**
```
>@>a>@>@@>b>@@>c
```
**Expected Output**
```
>c
```

---

### Test Case 9
**Input**
```
>alpha>beta>>@>gamma>@@>delta>@@@>epsilon>@@>zeta>>@>theta>@@>iota>@@>@@>kappa>lambda>>mu>@@>@@@>nu>@@>xi>@@>@@>omicron>@@>@@>pi>rho>sigma>@@@>tau>upsilon>@@>@@>phi>chi>psi>omega>
```
**Expected Output**
```
>alpha>beta>gamma>delta>@@@>epsilon>zeta>theta>iota>kappa>lambda>mu>@@@>nu>@@>xi>@@>@@>omicron>@@>@@>pi>rho>sigma>@@@>tau>upsilon>phi>chi>psi>omega
```

---

### Test Case 10
**Input**
```
>root>@@>folder1>@>folder2>@@>folder3>@>@>folder4>@@>@@>folder5>folder6>@>@@>@@>folder7>@@>@@>@@>end>@@>data>cache>@@>core>memory>@>@@>unit>process>@@>@@>final
```
**Expected Output**
```
>data>core>final
```

---
