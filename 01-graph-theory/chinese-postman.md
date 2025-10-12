<img width="538" height="227" alt="image" src="https://github.com/user-attachments/assets/4f726801-3232-43e6-824f-de9708de94cd" />


## 🧩 Step 1: List vertices and edges (with weights)

Edges (bidirectional):

| Edge | Weight |
| ---- | ------ |
| A–B  | 5      |
| A–C  | 9      |
| A–D  | 6      |
| B–C  | 5      |
| C–D  | 4      |
| C–F  | 18     |
| D–E  | 7      |
| E–F  | 4      |
| F–G  | 6      |
| G–H  | 7      |
| F–H  | 12     |
| E–H  | 10     |

---

## 🧮 Step 2: Find degree of each vertex

| Vertex | Connected to | Degree | Parity |
| ------ | ------------ | ------ | ------ |
| A      | B, C, D      | 3      | Odd    |
| B      | A, C         | 2      | Even   |
| C      | A, B, D, F   | 4      | Even   |
| D      | A, C, E      | 3      | Odd    |
| E      | D, F, H      | 3      | Odd    |
| F      | C, E, G, H   | 4      | Even   |
| G      | F, H         | 2      | Even   |
| H      | F, G, E      | 3      | Odd    |

**Odd-degree vertices:** A, D, E, H

---

## 🧠 Step 3: Find shortest paths between all odd vertices

We need shortest distances among A, D, E, H.

| Pair | Shortest Path      | Distance            |
| ---- | ------------------ | ------------------- |
| A–D  | Direct             | 6                   |
| A–E  | A–D–E              | 6 + 7 = **13**      |
| A–H  | A–D–E–H or A–C–F–H | 6 + 7 + 10 = **23** |
| D–E  | Direct             | 7                   |
| D–H  | D–E–H              | 7 + 10 = **17**     |
| E–H  | Direct             | 10                  |

---

## ⚖️ Step 4: Pair the odd vertices (minimum-weight matching)

We need to pair A, D, E, H into two pairs with minimum total distance.

Possible pairings:

| Pairing       | Total Distance    |
| ------------- | ----------------- |
| (A–D) + (E–H) | 6 + 10 = **16** ✅ |
| (A–E) + (D–H) | 13 + 17 = 30      |
| (A–H) + (D–E) | 23 + 7 = 30       |

✅ **Minimum pairing** = (A–D) and (E–H)

---

## 🛠️ Step 5: Duplicate edges along shortest paths

We’ll duplicate edges:

* A–D (6)
* E–H (10)

This makes all vertices even-degree.

---

## 📏 Step 6: Total Chinese Postman route length

Sum of all edges =
5 + 9 + 6 + 5 + 4 + 18 + 7 + 4 + 6 + 7 + 12 + 10 = **93**

Add duplicated edges (6 + 10 = 16):
Total route = **93 + 16 = 109**

---

✅ **Final Answer:**

* **Chinese Postman (minimum closed route) = 109**
* **Duplicated edges:** A–D and E–H
* **Graph becomes Eulerian after duplication.**
