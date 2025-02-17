# 1466 - Reorder Routes to Make All Paths Lead to the City Zero

## **❓ Problem:**

🔗[ LeetCode 1466 - Reorder Routes to Make All Paths Lead to the City Zero](https://leetcode.com/problems/reorder-routes-to-make-all-paths-lead-to-the-city-zero)

***

## **📝 Mô tả:**

Bạn được cung cấp **n thành phố** được đánh số từ `0` đến `n-1`, cùng với một danh sách các `connections`, trong đó mỗi `connections[i] = [a, b]` thể hiện một **con đường một chiều** từ thành phố `a` đến thành phố `b`.

Bạn cần tìm **số lượng con đường tối thiểu** cần được **đảo ngược hướng** sao cho tất cả các thành phố có thể đi đến thành phố `0`.

***

## **💡 Ví dụ:**

#### ✅ **Ví dụ 1:**

**Input:**

```
n = 6  
connections = [[0,1],[1,3],[2,3],[4,0],[4,5]]
```

**Output:**

```
3
```

**Giải thích:**\
Ta cần đảo ngược 3 đường `1 → 3`, `2 → 3`, `4 → 5` để đảm bảo tất cả thành phố có thể đi đến `0`.

***

#### ✅ **Ví dụ 2:**

**Input:**

```
n = 5  
connections = [[1,0],[1,2],[3,2],[3,4]]
```

**Output:**

```
2
```

**Giải thích:**\
Ta cần đảo ngược 2 đường `3 → 2`, `3 → 4` để tất cả có thể đi đến `0`.

***

## **🚀 Giải pháp**

Bài toán có thể được giải quyết bằng **DFS hoặc BFS trên đồ thị** như sau:

#### 🔹 **Phân tích**

1. **Chuyển đổi dữ liệu**:
   * Xây dựng đồ thị **vô hướng** từ danh sách `connections`, nhưng **đánh dấu hướng của các cạnh ban đầu**.
   * Mỗi cạnh `(a, b)` có hướng từ `a → b`, ta lưu thành `graph[a].append((b, 1))` và `graph[b].append((a, 0))`.
   * `1` có nghĩa là **cần đảo ngược** để dẫn về `0`.
   * `0` có nghĩa là **đã đúng hướng**.
2. **Duyệt DFS/BFS** từ `0`, đếm số cạnh phải đảo ngược.

***

## **📜 Code**

{% tabs %}
{% tab title="C++" %}
```cpp
class Solution {
public:
    int minReorder(int n, vector<vector<int>>& connections) {
        vector<vector<pair<int, int>>> graph(n);
        for (auto& conn : connections) {
            graph[conn[0]].push_back({conn[1], 1}); // Đường có hướng
            graph[conn[1]].push_back({conn[0], 0}); // Đường ngược chiều
        }

        int count = 0;
        vector<bool> visited(n, false);
        function<void(int)> dfs = [&](int node) {
            visited[node] = true;
            for (auto& [neighbor, needsReversal] : graph[node]) {
                if (!visited[neighbor]) {
                    count += needsReversal;
                    dfs(neighbor);
                }
            }
        };

        dfs(0);
        return count;
    }
};
```
{% endtab %}

{% tab title="Java" %}
```java
class Solution {
    public int minReorder(int n, int[][] connections) {
        List<int[]>[] graph = new ArrayList[n];
        for (int i = 0; i < n; i++) graph[i] = new ArrayList<>();

        for (int[] conn : connections) {
            graph[conn[0]].add(new int[]{conn[1], 1}); // Đường có hướng
            graph[conn[1]].add(new int[]{conn[0], 0}); // Đường ngược
        }

        boolean[] visited = new boolean[n];
        return dfs(0, graph, visited);
    }

    private int dfs(int node, List<int[]>[] graph, boolean[] visited) {
        visited[node] = true;
        int count = 0;

        for (int[] neighbor : graph[node]) {
            if (!visited[neighbor[0]]) {
                count += neighbor[1] + dfs(neighbor[0], graph, visited);
            }
        }
        return count;
    }
}
```
{% endtab %}

{% tab title="Python" %}
```python
class Solution:
    def minReorder(self, n: int, connections: List[List[int]]) -> int:
        from collections import defaultdict

        graph = defaultdict(list)
        for a, b in connections:
            graph[a].append((b, 1))  # Đường có hướng
            graph[b].append((a, 0))  # Đường ngược

        visited = set()
        def dfs(node):
            visited.add(node)
            return sum(needsReversal + dfs(neighbor) 
                       for neighbor, needsReversal in graph[node] if neighbor not in visited)

        return dfs(0)
```
{% endtab %}
{% endtabs %}

***

## **🎯 Điểm chính**

✔ **Biến đồ thị có hướng thành đồ thị vô hướng**, nhưng **đánh dấu hướng của cạnh ban đầu**.\
✔ **Dùng DFS hoặc BFS để duyệt từ node `0`**, đếm số cạnh cần đảo ngược.\
✔ **Thời gian `O(n)`, không gian `O(n)`, vì duyệt qua tất cả `n` đỉnh và `n-1` cạnh.**

***

## **⏳ Độ phức tạp thuật toán**

| Phương pháp   | Thời gian | Không gian |
| ------------- | --------- | ---------- |
| **DFS / BFS** | `O(n)`    | `O(n)`     |

* `O(n)` là do duyệt qua toàn bộ các cạnh và đỉnh trong cây.

***

## **📌 Tổng kết**

* **Bài toán yêu cầu đếm số cạnh cần đảo ngược để mọi node có thể đi đến `0`.**
* **DFS/BFS trên đồ thị có hướng giúp giải quyết bài toán một cách hiệu quả.**
* **Sử dụng đồ thị vô hướng nhưng đánh dấu hướng ban đầu giúp dễ dàng theo dõi.**
* **Thời gian `O(n)`, không gian `O(n)`, rất tối ưu.**
