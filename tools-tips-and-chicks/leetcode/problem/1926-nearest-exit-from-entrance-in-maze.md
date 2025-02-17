# 1926 - Nearest Exit from Entrance in Maze

## **❓ Problem:**

🔗[ LeetCode 1926 - Nearest Exit from Entrance in Maze](https://leetcode.com/problems/nearest-exit-from-entrance-in-maze)

***

## **📝 Mô tả:**

Cho một mê cung `maze` dạng lưới `m x n` chỉ chứa `.` (ô trống) và `+` (tường). Bạn bắt đầu tại `entrance` (`maze[i][j] = '.'`).

Nhiệm vụ là **tìm số bước ít nhất để đi đến lối ra gần nhất** (lối ra là **bất kỳ ô nào nằm trên biên của lưới, trừ ô `entrance`**). Nếu không thể tìm thấy lối ra, trả về `-1`.

***

## **💡 Ví dụ:**

#### ✅ **Ví dụ 1:**

**Input:**

```
maze = [["+","+",".","+"],  
        ["+",".",".","+"],  
        ["+","+","+","+"]],  
entrance = [1,2]
```

**Output:**

```
1
```

**Giải thích:**

* Lối vào ở `(1,2)`, chỉ cần di chuyển **1 bước** sang trái `(1,1)` để đến lối ra.

***

#### ✅ **Ví dụ 2:**

**Input:**

```
maze = [["+","+","+"],  
        [".",".","."],  
        ["+","+","+"]],  
entrance = [1,0]
```

**Output:**

```
2
```

**Giải thích:**

* Lối vào ở `(1,0)`, cần đi xuống `(2,0)`, sau đó sang phải `(1,1)`, tổng **2 bước** để đến lối ra.

***

#### ✅ **Ví dụ 3:**

**Input:**

```
maze = [[".","+"]],  
entrance = [0,0]
```

**Output:**

```
-1
```

**Giải thích:**

* Lối vào là biên duy nhất nên không có lối ra hợp lệ.

***

## **🚀 Giải pháp**

#### **🔹 Ý tưởng:**

* Đây là bài toán tìm đường ngắn nhất trong **lưới 2D** với trọng số bằng nhau (`1 bước`).
* **Breadth-First Search (BFS)** là cách tối ưu nhất để tìm **đường đi ngắn nhất** trong đồ thị không trọng số.

***

## **📜 Code**

{% tabs %}
{% tab title="C++" %}
```cpp
class Solution {
public:
    int nearestExit(vector<vector<char>>& maze, vector<int>& entrance) {
        int m = maze.size(), n = maze[0].size();
        queue<pair<int, int>> q;
        q.push({entrance[0], entrance[1]});
        maze[entrance[0]][entrance[1]] = '+'; // Đánh dấu đã thăm
        int steps = 0;

        vector<pair<int, int>> directions = {{1, 0}, {-1, 0}, {0, 1}, {0, -1}};
        
        while (!q.empty()) {
            int size = q.size();
            steps++;
            while (size--) {
                auto [x, y] = q.front(); q.pop();
                for (auto [dx, dy] : directions) {
                    int nx = x + dx, ny = y + dy;
                    if (nx >= 0 && ny >= 0 && nx < m && ny < n && maze[nx][ny] == '.') {
                        if (nx == 0 || ny == 0 || nx == m-1 || ny == n-1) return steps;
                        q.push({nx, ny});
                        maze[nx][ny] = '+'; // Đánh dấu đã thăm
                    }
                }
            }
        }
        return -1;
    }
};
```
{% endtab %}

{% tab title="Java" %}
```java
class Solution {
    public int nearestExit(char[][] maze, int[] entrance) {
        int m = maze.length, n = maze[0].length;
        Queue<int[]> q = new LinkedList<>();
        q.offer(new int[]{entrance[0], entrance[1]});
        maze[entrance[0]][entrance[1]] = '+';
        int steps = 0;
        
        int[][] directions = {{1, 0}, {-1, 0}, {0, 1}, {0, -1}};
        
        while (!q.isEmpty()) {
            steps++;
            int size = q.size();
            for (int i = 0; i < size; i++) {
                int[] cur = q.poll();
                int x = cur[0], y = cur[1];
                for (int[] dir : directions) {
                    int nx = x + dir[0], ny = y + dir[1];
                    if (nx >= 0 && ny >= 0 && nx < m && ny < n && maze[nx][ny] == '.') {
                        if (nx == 0 || ny == 0 || nx == m-1 || ny == n-1) return steps;
                        q.offer(new int[]{nx, ny});
                        maze[nx][ny] = '+';
                    }
                }
            }
        }
        return -1;
    }
}
```
{% endtab %}

{% tab title="Python" %}
```python
from collections import deque

class Solution:
    def nearestExit(self, maze: List[List[str]], entrance: List[int]) -> int:
        m, n = len(maze), len(maze[0])
        q = deque([(entrance[0], entrance[1])])
        maze[entrance[0]][entrance[1]] = '+'
        steps = 0

        directions = [(1, 0), (-1, 0), (0, 1), (0, -1)]
        
        while q:
            steps += 1
            for _ in range(len(q)):
                x, y = q.popleft()
                for dx, dy in directions:
                    nx, ny = x + dx, y + dy
                    if 0 <= nx < m and 0 <= ny < n and maze[nx][ny] == '.':
                        if nx == 0 or ny == 0 or nx == m-1 or ny == n-1:
                            return steps
                        q.append((nx, ny))
                        maze[nx][ny] = '+'
        return -1
```
{% endtab %}
{% endtabs %}

***

## **🎯 Điểm chính**

✔ **BFS là cách tối ưu** vì nó tìm đường đi ngắn nhất trong đồ thị không trọng số.\
✔ **Sử dụng hàng đợi (`queue`) để kiểm soát thứ tự duyệt theo từng bước**.\
✔ **Đánh dấu ô đã thăm (`'+'`) để tránh lặp lại**.\
✔ **Bắt đầu từ `entrance`, mở rộng ra các hướng cho đến khi tìm thấy lối ra**.

***

## **⏳ Độ phức tạp thuật toán**

| Phương pháp | Thời gian  | Không gian |
| ----------- | ---------- | ---------- |
| **BFS**     | `O(m * n)` | `O(m * n)` |

* `O(m * n)`: duyệt qua toàn bộ lưới trong trường hợp xấu nhất.
* Không gian `O(m * n)`: dùng `queue` để lưu các ô cần kiểm tra.

***

## **📌 Tổng kết**

* ✅ **Bài toán này là tìm đường đi ngắn nhất trong lưới -> BFS là lựa chọn tốt nhất.**
* ✅ **Cần đánh dấu ô đã thăm để tránh lặp vô hạn.**
* ✅ **Thời gian chạy `O(m * n)`, không gian `O(m * n)`, tối ưu cho bài toán.**
