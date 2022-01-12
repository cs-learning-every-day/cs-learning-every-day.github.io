### Basic

#### Quick Sort

```c++
void quick_sort(int q[], int l, int r)
{
    if (l >= r) return;

    int i = l - 1, j = r + 1, x = q[l + r >> 1];
    while (i < j)
    {
        do i ++ ; while (q[i] < x);
        do j -- ; while (q[j] > x);
        if (i < j) swap(q[i], q[j]);
    }
    quick_sort(q, l, j), quick_sort(q, j + 1, r);
}
```

#### Merge Sort

```c++
void merge_sort(int q[], int l, int r)
{
    if (l >= r) return;

    int mid = l + r >> 1;
    merge_sort(q, l, mid);
    merge_sort(q, mid + 1, r);

    int k = 0, i = l, j = mid + 1;
    while (i <= mid && j <= r)
        if (q[i] <= q[j]) tmp[k ++ ] = q[i ++ ];
        else tmp[k ++ ] = q[j ++ ];

    while (i <= mid) tmp[k ++ ] = q[i ++ ];
    while (j <= r) tmp[k ++ ] = q[j ++ ];

    for (i = l, j = 0; i <= r; i ++, j ++ ) q[i] = tmp[j];
}
```

#### Binary Search
```c++
// 区间[l,r]划分成[l, mid], [mid + 1, r]
void binary_search1(int l, int r) {
    while (l < r) {
        int mid = l + r >> 1;
        if (check(mid)) { //check() 检查mid是否满足性质
            r = mid;
        } else {
            l = mid + 1;
        }
    }
}
// 区间[l,r]划分成[l, mid - 1], [mid, r]
void binary_search2(int l, int r) {
    while (l < r) {
        int mid = l + r + 1>> 1;
        if (check(mid)) {
            l = mid;
        } else {
            r = mid - 1;
        }
    }
}
```