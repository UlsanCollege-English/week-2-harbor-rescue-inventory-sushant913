# 🚤 Harbor Rescue Inventory System

## 📌 Summary
This project builds a small inventory system for a harbor rescue team using Python lists.  
Each function helps inspect or manage supplies stored on boats.  

The assignment focuses on:
- writing clear functions with proper return values  
- working with list indexing and slicing  
- handling edge cases safely  
- understanding basic time complexity  

---

## 🛠️ Approach

### mission_snapshot
- Return the first and last item using indexing
- Handle empty list by returning `(None, None)`
- If one item, return it twice

---

### cargo_window
- Check if `start` is valid
- Check if `size > 0`
- Use slicing to return items from `start` to `start + size`
- Python slicing automatically prevents overflow errors

---

### first_supply_index
- Loop through the list using `enumerate`
- Return index when target is found
- If not found, return `-1`

---

### supply_report
- Loop through list
- Count occurrences of target
- Track first index when first seen
- If not found, return `(0, -1)`

---

### priority_load (Stretch)
- Create a new list with `[urgent_item] + items`
- Do NOT modify original list

---

## ⏱️ Complexity Reasoning

### mission_snapshot
- **Time:** O(1)  
- Accessing first and last elements directly  

---

### cargo_window
- **Time:** O(k)  
- Where `k = size` (slice length)  
- Slicing copies elements into a new list  

---

### first_supply_index
- **Time:** O(n)  
- In worst case, must check every element  

---

### supply_report
- **Time:** O(n)  
- Single loop to count and find first index  

---

### priority_load
- **Time:** O(n)  
- Creating a new list requires copying all elements  

💡 Adding to the front is expensive because:
- Python lists are arrays
- All elements must shift right → O(n)
- Accessing by index is fast → O(1)

---

## ⚠️ Edge Case Checklist

- [x] Empty list  
- [x] One-item list  
- [x] Target missing  
- [x] Repeated values  
- [x] Slice goes past end  
- [x] Size is zero or negative  
- [x] Start index out of range  
- [x] Original list unchanged (priority_load)  

---

## 🧪 Testing

Run tests using:

```bash
pytest -q