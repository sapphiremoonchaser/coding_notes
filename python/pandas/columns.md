🌴💜✨ Pandas Column Ops — Neon Tropical Synthwave Edition ✨💙🌺

A glowing quick-reference for adding, updating, renaming, and transforming columns in pandas.
Vibes: synthwave, neon lights, Miami sunset, tropical nights. 🌅🌴💫

---

## 🌈 List Columns  

`df.columns`

---

## 🦩 Adding + Updating Columns
`df["new_col"] = df["age"] * 2`  

`df["is_adult"] = df["age"].apply(lambda x: x >= 18)`  

`df["constant"] = 1`

---

#### 🌺 Using .assign() (clean + chainable)
```
df = df.assign(
    score=df.age * 1.5
)
```

---

## 🌴💫 Renaming Columns

```
df = df.rename(
    columns={
        "old": "new"
    }
)
```

🐚✨ Rename to lowercase, snake_case, etc.

`df.columns = df.columns.str.lower()`  

`df.columns = df.columns.str.replace(" ", "_")`

---

## 🌊 Apply, Map, Applymap (Transformation Trio)

💜 Apply on a Single Column

```
df['double'] = df['num'].apply(
    lambda x: x * 2
)
```

🌈 Map on a Column (great for dict lookups)

```
df['grade'] = df['score'].map({
    90: "A",
    80: "B"
})
```

🌴 Apply on the Entire DataFrame

```
df.applymap(
    lambda x: x if isinstance(x, str) else round(x, 2)
)
```

