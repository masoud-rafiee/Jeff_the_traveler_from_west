
# Jeff's Journey from West to East 🚀

## 🧠 Objective

Jeff wants to travel from the **West to the East**. Your task is to determine the **maximum number of cities** he can visit along the way, following these two strict travel rules:

### ✨ Travel Rules

1. **Lexicographic Order**  
   Jeff may only move to cities whose names come **later in alphabetical order**.  
   _Example: He **cannot** go from “Berkeley” to “Albany” or from “City2” to “City100”._

2. **Increasing Distance (Eastward Only)**  
   Jeff may only move to cities that are **further East** than his current location (i.e., **distance must increase**).  
   _Example: If Jeff is at “Berkeley” (distance = 50), he **cannot** go to any city with a smaller distance._

---

## 🛠️ Function Signature

```python
def MaxCities(cities: List[str], distances: List[int]) -> int:
```

### Parameters

- `cities`: A list of city names (`List[str]`)
- `distances`: A list of unique integers (`List[int]`) representing each city’s distance from the West  
  > The `i-th` value in `distances` corresponds to the city in `cities[i]`.

### Returns

- An integer — the **maximum number of cities** Jeff can visit while following the two rules.

---

## 📦 Example

```python
cities = ['Tucson', 'Albany', 'Smith', 'Westford', 'Berkeley']
distances = [102, 95, 114, 1421, 50]
result = MaxCities(cities, distances)  # Output: 3
```

### ✅ Explanation:

One possible valid sequence Jeff can follow is:

1. **Berkeley** (distance = 50)  
2. → **Tucson** (distance = 102; lex > Berkeley)  
3. → **Westford** (distance = 1421; lex > Tucson)  

This path satisfies both the lexicographic and distance constraints.  
So, the answer is `3`.

---

## 📌 Constraints

- `1 ≤ len(cities) == len(distances) ≤ 10,000`
- All distances are unique integers between `1` and `9999` inclusive.
- All city names are valid non-empty strings.

---

## 💡 Hint

This is a variant of the classic **Longest Increasing Subsequence (LIS)** problem, but with **two constraints**:
- Alphabetical order on city names
- Numerical order on distances

You can solve this efficiently using **dynamic programming**, and for optimized solutions consider using **coordinate compression + segment trees** or **binary search** on both constraints.

---

## 🔚 Goal

Maximize the number of cities Jeff can visit by building the **longest valid path** from West to East using the above rules.
