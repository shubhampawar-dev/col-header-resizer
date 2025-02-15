Here's a full **README.md** file with detailed usage, installation, customization, and contribution guidelines for your GitHub repository.  

---

### 📜 **README.md** (Complete Documentation)  

```md
# jQuery Resizable Table Extension

A lightweight jQuery plugin that enables column resizing for HTML tables, including support for DataTables.

## 🚀 Features

✅ Resizable table columns with smooth dragging  
✅ Works with standard HTML tables  
✅ Fully compatible with jQuery DataTables  
✅ Prevents column width shifting  
✅ Minimum column width enforced  

---

## 📌 Installation

### 1️⃣ **Include Dependencies**
Add the required dependencies in your HTML file:

```html
<!-- jQuery -->
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>

<!-- DataTables (optional, only if using with DataTables) -->
<script src="https://cdn.datatables.net/1.13.6/js/jquery.dataTables.min.js"></script>
<link rel="stylesheet" href="https://cdn.datatables.net/1.13.6/css/jquery.dataTables.min.css">
```

### 2️⃣ **Include Plugin Files**
Download the `resizable-table.min.js` and `resizable-table.css` files and include them in your project:

```html
<!-- Resizable Table Plugin -->
<link rel="stylesheet" href="resizable-table.css">
<script src="resizable-table.min.js"></script>
```

---

## ⚙️ Usage

### 📌 **Basic Resizable Table**
```html
<table class="table-resizable">
    <thead>
        <tr>
            <th>Name</th>
            <th>Email</th>
            <th>Phone</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>John Doe</td>
            <td>john@example.com</td>
            <td>+1234567890</td>
        </tr>
    </tbody>
</table>

<script>
    $(document).ready(function () {
        $('.table-resizable').resizableTable();
    });
</script>
```

### 📌 **Using with DataTables**
```html
<table id="myTable" class="table-resizable display">
    <thead>
        <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Email</th>
        </tr>
    </thead>
</table>

<script>
    $(document).ready(function () {
        var table = $('#myTable').DataTable({
            ajax: "data.json",
            columns: [
                { data: "id" },
                { data: "name" },
                { data: "email" }
            ]
        });

        $(table.table().node()).resizableTable();
    });
</script>
```

---

## 🎨 CSS Styling

To customize the appearance, modify `resizable-table.css`:

```css
.resizable-table {
    width: 100%;
    border-collapse: collapse;
}

.resizable-table th,
.resizable-table td {
    position: relative;
    padding: 10px;
    border: 1px solid #ddd;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}

.resizable-table th {
    background: #f4f4f4;
    font-weight: bold;
}

.resize-handle {
    cursor: col-resize;
    position: absolute;
    right: 0;
    top: 0;
    width: 8px;
    height: 100%;
    background: rgba(0, 0, 0, 0.1);
    transition: background 0.2s;
}

.resize-handle:hover {
    background: rgba(0, 0, 0, 0.3);
}

.resizable-table th:hover .resize-handle {
    background: rgba(0, 0, 0, 0.2);
}
```

---

## 🛠️ Customization

### ✅ **Minimum Column Width**
To change the minimum width, update the `resizable-table.min.js`:

```js
if (newWidth > 50) { // Change "50" to desired minimum width
```

### ✅ **Resizable Handle Width**
Modify `.resize-handle` width in CSS:

```css
.resize-handle {
    width: 10px; /* Default: 8px */
}
```

### ✅ **Disable Resizing on Specific Columns**
To prevent resizing for specific columns, remove the `.resize-handle` div from those `th` elements.

---

## 🔍 Troubleshooting

### ❓ **Column width is shifting when resizing**
Ensure the table has a fixed layout by adding:

```css
table {
    table-layout: fixed;
}
```

### ❓ **Resizing not working with DataTables**
Make sure the script is applied after DataTable initialization:

```js
var table = $('#myTable').DataTable();
$(table.table().node()).resizableTable();
```

---

## 📄 License

This project is licensed under the **MIT License**. You are free to modify and use it in any project.

---

## 🤝 Contributing

Contributions are welcome! Follow these steps:

1. **Fork the repository**  
2. **Create a new branch**: `git checkout -b feature-branch`  
3. **Commit your changes**: `git commit -m "Added new feature"`  
4. **Push to GitHub**: `git push origin feature-branch`  
5. **Submit a Pull Request**  

For major changes, please open an issue first to discuss the proposed changes.

---

## ⭐ Support

If you find this project useful, please consider giving it a **star ⭐** on GitHub.

---

Happy Coding! 🚀
```

---

