### MIN To MAX


---

### 🧩 **Problem Goal**

You have an array of integers. In one operation, you can replace any number with an integer from 1 to 100. Your goal is to **make the smallest value in the original array (`M`) become the maximum value in the array**.

To do that, you need to **reduce or replace all the elements that are greater than `M`**, because `M` can't be the maximum while larger numbers still exist.

---

### 🔍 **How the Code Works**

```cpp
int T;
cin >> T;
```

* Reads the number of test cases.

---

```cpp
while (T--) {
    int N;
    cin >> N;
    vector<int> A(N);
```

* For each test case, read the size of the array `N` and declare the vector `A` of size `N`.

---

```cpp
for (int i = 0; i < N; ++i) {
    cin >> A[i];
}
```

* Read all `N` elements of the array.

---

```cpp
int M = *min_element(A.begin(), A.end());
```

* Find the **minimum value `M`** in the array. This is the value we want to become the **new maximum**.

---

```cpp
int operations = 0;
for (int i = 0; i < N; ++i) {
    if (A[i] > M) {
        operations++;
    }
}
```

* Count how many elements are **greater than `M`**. Each such element must be replaced (with some number ≤ `M`), which counts as one operation.

---

```cpp
cout << operations << endl;
```

* Print the result: the minimum number of operations needed.

---

### 🧠 **Example**

Input:

```
1
5
3 1 4 1 5
```

* Minimum = `1`
* Numbers greater than 1 = `3`, `4`, `5` → total of **3 numbers**
* Output: `3`

---

