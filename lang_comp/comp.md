### This note compares the differences of languanges
### Java, Python, TypeScript

----------

#### Data structures overview

| type  |  Java | Python | TypeScript  |
|---|---|---|---|
|Array |`T[]`|`[]`| `[]`|
|Dynamic array| `ArrayList<T>`|`[]`|`[]`|
|list| `LinkedList<T>`| `N/A`| `N/A`|
|OrderedSet<br>OrderedMap|`TreeSet<T>`<br>`TreeMap<T>`| `sortedcontainers package`<br>`SortedSet()` `SortedMap()` |`N/A`|
|HashSet<br>HashMap|`HashSet<T>`<br>`HashMap<T>`| `set()`<br>`dict()` | `Set<T>`<br>`Map<T>` | 
|Heap| `PriorirtyQueue<T>` | `heapq` |`datastructures-js/priority-queue package` |
|Queue<bt>Deque| `Queue<T>`<br>`Deque<T>`| `collections.deque()`|`datastructures-js/queue package`| 
|Stack| `Stack<T>` | `[]` | `[]` |
|Pair<br>Tuple| `Pair class`|`(x, y, z)`| `[]`|
|Customized| `class`| `class, tuple`| `class`|

#### Array

| |Java|Python|TypeScript|
|---|---|---|---|
|1D| `int[] a = new int[]{1, 2, 3};`| `a = [1, 2, 3]`| `const a = [1, 2, 3]` |
|1D init to x| `int[] a = new int[n];`<br>`Array.fill(a, x);`| `a = [x] * n`| `const a = new Array(n)`<br>`a.fill(x)` |
|2D init to x| `int[][] a = new int[m][n];`<br>`for (int[] row : a)`<br> &emsp;`Array.fill(a, x)`| `a = [[x] * n for _ in range(m)]`| `const a = [...Array(m)].map(_=>Array(n).fill(x)) `|
|3D init to x| `int[][][] a = new int[k][m][n];`<br>`for (int[][] mat : a)`<br> &emsp;`for (int[] row : mat)` <br> &emsp; &emsp; `Array.fill(row, x)`| `a = [[[x] * n for _ in range(m)] for _ in range(k)]`| `const a = [...Array(k)].map(_ => [...Array(m)].map(_ => Array(n).fill(x)))`   |

#### Dynamic array

| |Java|Python|TypeScript|
|---|---|---|---|
|init|`List<Integer> a = new ArrayList<>();`|`a = []`| `const a = []`|
|add|`a.add(x)`|`a.append(x)`| `a.push(x)`|
|remove last|`a.remove(a.size() - 1)`| `a.pop()`<br>`del a[-1]` | `a.pop()`|
|access with index<bt>access last|`a.get(index)`<br>`a.get(a.size() - 1)`|`a[index]`<br>`a[-1]`| `a[index]`<br>`a[a.length - 1]` |

#### HashTable

| |Java|Python|TypeScript|
|---|---|---|---|
|init|`Map<Integer, Integer> m = new HashMap<>();`| `m = dict()`|`const m: Map<number, number> = new Map()`|
|insert|`m.put(k, v)`| `m[k] = v` |`m.set(k, v)`|
|get| `v = m.get(k)`<br>`v = m.getOrDefault(k, d)`| `v = m[k]`| `m.get(k)`|
|contain| `m.containsKey(k)`| `k in m` | `m.has(k)`|
|iterate| `for (Integer k : m.keySet())`<br> &emsp; `v = m.get(k)` <br> `for(Map.Entry<Integer, Integer> entry: m.entrySet())`<br> &emsp; `entry.getKey(); entry.getValue();` | `for k in m:` <br> &emsp; `v = a[k]` <br> `for k, v in m.items():` <br> &emsp; `pass`|`for (const k of m.keys())` <br> &emsp;`const v = m.get(k)` <br> `for (const [k, v] of m)` <br> &emsp; `// use k and v`| 

#### PriorityQueue / Heap

| |Java (min heap)|Python (min heap)|TypeScript|
|---|---|---|---|
|init|`Queue<Integer> q = new PriorityQueue<Integer>();`|`q = []`| |
|init from array <br> (heapify)|`List<Integer> a = ...;`<br>`Queue<Integer> q = new PriorityQueue<Integer>(a);`| `q = [2, 1, 3, 4]`<br>`heapq.heapify(q)`| |
|insert|`q.offer(x)`|`heapq.heappush(q, x)`| |
|peek| `q.peek()`| `q[0]`| |
|pop| `q.poll()`| `heapq.heappop(q)`| | 
