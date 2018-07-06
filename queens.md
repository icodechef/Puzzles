N皇后问题
=========

#### 递归法

python代码如下：

```python
def ok(state, row, col):
    for i in range(row):
        pos = state[i]
        if pos == col or abs(pos - col) == row - i:
            return False
    return True


def queens(state, row):
    if row == len(state):
        results.append(state)
    else:
        for col in range(len(state)):
            if ok(state, row, col):
                state[row] = col
                queens(state, row + 1)


results = []
state = [-1] * 8
queens(state, 0)

print(len(results))
