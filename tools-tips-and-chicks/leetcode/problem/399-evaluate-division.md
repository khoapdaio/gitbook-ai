# 399 - Evaluate Division

## **❓ Problem:**

[🔗 LeetCode 399 - Evaluate Division](https://leetcode.com/problems/evaluate-division)

***

## **📝 Mô tả:**

Cho một danh sách các phương trình dưới dạng `equations[i] = [Ai, Bi]` đại diện cho biểu thức toán học `Ai / Bi = values[i]`, bạn cần tính toán giá trị của các truy vấn được cung cấp trong `queries[j] = [Cj, Dj]`.

Nếu có thể tính giá trị của `Cj / Dj`, hãy trả về giá trị đó, nếu không trả về `-1.0`.

***

## **💡 Ví dụ:**

#### ✅ **Ví dụ 1:**

**Input:**

```
equations = [["a","b"],["b","c"]],  
values = [2.0,3.0],  
queries = [["a","c"],["b","a"],["a","e"],["a","a"],["x","x"]]
```

**Output:**

```
[6.00000, 0.50000, -1.00000, 1.00000, -1.00000]
```

**Giải thích:**

* `a / c = (a / b) * (b / c) = 2.0 * 3.0 = 6.0`
* `b / a = 1 / (a / b) = 1 / 2.0 = 0.5`
* `a / e`: không có thông tin nên trả về `-1.0`
* `a / a = 1.0`
* `x / x`: không tồn tại nên trả về `-1.0`

***

#### ✅ **Ví dụ 2:**

**Input:**

```
equations = [["x1","x2"],["x2","x3"],["x3","x4"],["x4","x5"]],  
values = [3.0,4.0,5.0,6.0],  
queries = [["x1","x5"],["x5","x2"],["x2","x4"],["x2","x2"],["x2","x9"],["x9","x9"]]
```

**Output:**

```
[360.00000, 0.00833, 20.00000, 1.00000, -1.00000, -1.00000]
```

**Giải thích:**

* `x1 / x5 = (x1 / x2) * (x2 / x3) * (x3 / x4) * (x4 / x5) = 3 * 4 * 5 * 6 = 360.0`
* `x5 / x2 = 1 / (x1 / x5) * (x1 / x2) = 1 / 360 * 3 = 0.00833`

***

## **🚀 Giải pháp**

Bài toán này yêu cầu **tìm giá trị giữa hai biến bằng cách sử dụng quan hệ đã biết**, có thể xem như **tìm đường đi giữa hai đỉnh trên đồ thị có trọng số**.

🔹 **Ý tưởng chính:**

1. **Xây dựng đồ thị có trọng số:**
   * Biểu thức `a / b = 2.0` được lưu thành `graph[a].append((b, 2.0))` và `graph[b].append((a, 1/2.0))`.
2. **Tìm đường đi giữa hai đỉnh bằng DFS hoặc BFS:**
   * Nếu có đường từ `Cj` đến `Dj`, ta nhân các trọng số trên đường đi để tính kết quả.
   * Nếu không có đường đi, trả về `-1.0`.

***

### **📜 Code**

{% tabs %}
{% tab title="C++" %}
```cpp
class Solution {
public:
    unordered_map<string, vector<pair<string, double>>> graph;
    
    double dfs(string src, string dst, unordered_set<string>& visited) {
        if (graph.find(src) == graph.end() || graph.find(dst) == graph.end()) return -1.0;
        if (src == dst) return 1.0;
        visited.insert(src);
        
        for (auto& [neighbor, value] : graph[src]) {
            if (visited.find(neighbor) == visited.end()) {
                double result = dfs(neighbor, dst, visited);
                if (result != -1.0) return result * value;
            }
        }
        return -1.0;
    }
    
    vector<double> calcEquation(vector<vector<string>>& equations, vector<double>& values, vector<vector<string>>& queries) {
        graph.clear();
        for (int i = 0; i < equations.size(); i++) {
            graph[equations[i][0]].push_back({equations[i][1], values[i]});
            graph[equations[i][1]].push_back({equations[i][0], 1.0 / values[i]});
        }
        
        vector<double> result;
        for (auto& query : queries) {
            unordered_set<string> visited;
            result.push_back(dfs(query[0], query[1], visited));
        }
        return result;
    }
};
```
{% endtab %}

{% tab title="Java" %}
```java
class Solution {
    Map<String, List<Pair<String, Double>>> graph = new HashMap<>();

    public double dfs(String src, String dst, Set<String> visited) {
        if (!graph.containsKey(src) || !graph.containsKey(dst)) return -1.0;
        if (src.equals(dst)) return 1.0;
        visited.add(src);

        for (Pair<String, Double> neighbor : graph.get(src)) {
            if (!visited.contains(neighbor.getKey())) {
                double result = dfs(neighbor.getKey(), dst, visited);
                if (result != -1.0) return result * neighbor.getValue();
            }
        }
        return -1.0;
    }

    public double[] calcEquation(List<List<String>> equations, double[] values, List<List<String>> queries) {
        graph.clear();
        for (int i = 0; i < equations.size(); i++) {
            graph.computeIfAbsent(equations.get(i).get(0), k -> new ArrayList<>()).add(new Pair<>(equations.get(i).get(1), values[i]));
            graph.computeIfAbsent(equations.get(i).get(1), k -> new ArrayList<>()).add(new Pair<>(equations.get(i).get(0), 1.0 / values[i]));
        }

        double[] result = new double[queries.size()];
        for (int i = 0; i < queries.size(); i++) {
            result[i] = dfs(queries.get(i).get(0), queries.get(i).get(1), new HashSet<>());
        }
        return result;
    }
}
```
{% endtab %}

{% tab title="Python" %}
```python
class Solution:
    def calcEquation(self, equations: List[List[str]], values: List[float], queries: List[List[str]]) -> List[float]:
        from collections import defaultdict

        graph = defaultdict(list)
        for (a, b), value in zip(equations, values):
            graph[a].append((b, value))
            graph[b].append((a, 1.0 / value))

        def dfs(src, dst, visited):
            if src not in graph or dst not in graph:
                return -1.0
            if src == dst:
                return 1.0
            visited.add(src)
            for neighbor, value in graph[src]:
                if neighbor not in visited:
                    result = dfs(neighbor, dst, visited)
                    if result != -1.0:
                        return result * value
            return -1.0

        return [dfs(q[0], q[1], set()) for q in queries]
```
{% endtab %}
{% endtabs %}

***

## **🎯 Điểm chính**

✔ **Xây dựng đồ thị có trọng số từ danh sách phương trình**\
✔ **Sử dụng DFS để tìm đường đi giữa hai đỉnh, tính kết quả bằng cách nhân các trọng số**\
✔ **Nếu không tìm thấy đường đi, trả về `-1.0`**

***

## **⏳ Độ phức tạp thuật toán**

| Phương pháp | Thời gian  | Không gian |
| ----------- | ---------- | ---------- |
| **DFS/BFS** | `O(N + Q)` | `O(N)`     |

* `N` là số phương trình, `Q` là số truy vấn.
* **Xây dựng đồ thị:** `O(N)`
* **Duyệt DFS/BFS cho mỗi truy vấn:** `O(Q)`
* **Không gian:** `O(N)`, lưu đồ thị.

***

## **📌 Tổng kết**

* **Bài toán này có thể được xem như tìm đường đi trên đồ thị có trọng số.**
* **Dùng DFS hoặc BFS để tính toán kết quả dựa trên trọng số cạnh.**
* **Độ phức tạp `O(N + Q)`, khá tối ưu.**
