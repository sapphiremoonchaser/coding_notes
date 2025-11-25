🐼✨ Pandas .agg() Cheat Sheet — NEON EDITION ✨🐼

Your glowing guide to every aggregation you can use with `df.agg()` and `groupby().agg()`
💜💙🩵 Synthwave-friendly • Fast • Complete

---
🌈 1. Core Aggregations (String Names)
🔥 Basics

* "sum"
* "mean"
* "median"
* "min"
* "max"
* "count"
* "size"
* "nunique"

⚡ Stats

* "std" — standard deviation
* "var" — variance
* "sem" — standard error
* "skew"
* "kurt" / "kurtosis"

🌟 Position-Based

* "first"
* "last"
* "nth"
* "idxmin"
* "idxmax"

💫 Logic

* "any"
* "all"

🌺 String-Friendly

* "unique"
* "nunique"
* "count"
* "min"
* "max"

🪩 Percentiles

* "quantile" (use with lambda for %s)

```aiignore
df.groupby("team").agg(
    pct_95=("value", lambda x: x.quantile(0.95))
)
```

---

💜 2. NumPy Functions You Can Glow-Up With

* np.sum
* np.mean
* np.median
* np.min
* np.max
* np.std
* np.var
* np.prod
* np.percentile
* np.nanmean
* np.nansum
* np.nanstd
* np.nanvar  

⚠️ Tip: NumPy functions ignore pandas-specific metadata like index names.

---

💎 3. Python Built-ins That Work Inside .agg()

* len
* sum
* min
* max
* any
* all

---

## 🍒 Examples

#### Multi-Agg on one category

```aiignore
df.agg(
    ["min", "max", "mean"]
)
```

#### Multi-Agg on Multiple categories
  
```aiignore
df.agg({
    "age": ["min", "max", "mean"],
    "score": "sum"
})
```

#### Named Aggregations (Cleanest?)
  
```aiignore
df.groupby("team").agg(
    avg_age=("age", "mean"),
    score_range=("score", lambda x: x.max() - x.min()),
    pct_95=("value", lambda x: x.quantile(0.95))
)
```

#### Lambda Example
  
`df.agg({"col": lambda x: x.max() - x.min()})`

#### Custom Function

```aiignore
def iqr(s):
    return s.quantile(0.75) - s.quantile(0.25)

df.agg({"col": iqr})
```