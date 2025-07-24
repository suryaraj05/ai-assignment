
# Rabbit and Bridge Crossing Problem

---

## 🐇 Rabbit Question

### 🧠 Explanation

We have three **east rabbits** (`e1`, `e2`, `e3`) and three **west rabbits** (`w1`, `w2`, `w3`).

We represent their positions using a list:

```
["-", "e1", "e2", "e3", "-", "w1", "w2", "w3", "-"]
```

### 🔄 Move Generation Rules

- **East (e)** rabbits can only move **forward (++)**
- **West (w)** rabbits can only move **backward (--)**

#### Possible Moves:

1. A rabbit can move **1 or 2 steps** only if there is an empty space (`"-"`).
    - `e` can go `e+1` or `e+2`
    - `w` can go `w-1` or `w-2`
2. A rabbit can **jump over** another rabbit if there's an empty space after the jump.
    - `e` can go `e+2` if `e+1` has a rabbit and `e+2` is `"-"`
    - `w` can go `w-2` if `w-1` has a rabbit and `w-2` is `"-"`

### ✅ Goal Test

The goal is to have all **west rabbits** on the **left** and **east rabbits** on the **right**:

```
["w1", "w2", "w3", "-", "-", "-", "e1", "e2", "e3"]
```

---

## 🌉 Bridge Crossing Train Question

### 🧠 Explanation

There are four characters:

- **Amogh (Boy)**: 5 minutes
- **Ameya (Girl)**: 10 minutes
- **Grandma**: 20 minutes
- **Grandpa**: 25 minutes

They must all cross a bridge in **≤ 60 minutes**, with **only one umbrella**, and a **maximum of 2 people** can cross at a time.

We track:
- A `left` list and a `right` list of people
- A `time_left` counter
- The `umbrella` side (`left` or `right`)

### 🔄 Move Generation Rules

- If someone crosses the bridge, subtract **their max crossing time** from `time_left`
- Valid only if `time_left ≥ 0`
- Example time deductions:
    - Amogh crosses: `time_left - 5`
    - Ameya crosses: `time_left - 10`
    - Grandma crosses: `time_left - 20`
    - Grandpa crosses: `time_left - 25`

### ✅ Goal Test

The goal is achieved when:

- **Right side** has: `['Grandpa', 'Grandma', 'Amogh', 'Ameya']`
- **Left side** is empty: `[]`
- **Umbrella** is on the **right**
- **Time left ≥ 0`
