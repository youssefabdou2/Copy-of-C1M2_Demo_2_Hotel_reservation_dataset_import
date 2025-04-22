

---

## 🛠️ Data Processing Techniques (Hotel Reservations Dataset)

Cleaning and transforming raw data helps you:
- Simplify analysis  
- Improve model performance  
- Reveal patterns more clearly  

---

### 🔤 1. **Categorical Grouping with `IF()`**

#### ✅ Collapse meal plan categories  
Turn *NotSelected* → `0` and everything else → `1` (binary encoding).

```excel
=IF(B2="NotSelected", 0, 1)
```

- `B2`: Original meal plan value  
- Result: `HasMealPlan` column → 0 or 1

✅ Use autofill to apply to all rows  
✅ Add **conditional formatting** (e.g., green for 1, red for 0)

---

### 🧩 2. **Text Processing with `RIGHT()` or `LEFT()`**

#### ✅ Extract Room Type Number (e.g., “Room_Type 1” → “1”)
```excel
=RIGHT(C2, 1)
```
- `C2`: Original room type value  
- Great for simplifying display and analysis  

✅ Combine with `TEXT()` if needed for formatting

---

### 🧮 3. **Numerical Binning with `IFS()`**

#### ✅ Bin lead times:
- `< 50` → *Short*
- `50–99` → *Medium*
- `≥ 100` → *Long*

```excel
=IFS(D2<50, "Short", D2<100, "Medium", D2>=100, "Long")
```

- `D2`: Lead Time  
- Helps in plotting, summarizing, and categorizing continuous data

✅ Makes filtering easier  
✅ Excellent for dashboards & pivot tables

---

## 📊 When to Use These Techniques

| Technique         | When to Use                                                                 |
|------------------|------------------------------------------------------------------------------|
| `IF()`            | Binary categorization or value simplification                              |
| `RIGHT()`/`LEFT()`| Extracting identifiers, codes, or parts of strings                          |
| `IFS()`           | Creating labeled groups from continuous data (e.g., age, time, price)       |

---

## 🔄 Bonus Tips

- **Always create new columns** instead of modifying original data  
- **Label your columns clearly** (e.g., `LeadTime_Binned`, `RoomTypeNum`)  
- Combine with **COUNTIFS**, **SUMIFS**, and **PivotTables** for richer insight  
- Use **data validation** and **filters** for quick checks after transformation

---
