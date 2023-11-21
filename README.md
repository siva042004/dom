# JavaScript - 4 - DOM
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dynamic Table Generator</title>
    <style>
        table {
            border-collapse: collapse;
            width: 100%;
            margin-top: 20px;
        }

        table, th, td {
            border: 1px solid black;
        }

        th, td {
            padding: 10px;
            text-align: center;
        }
    </style>
</head>
<body>

    <div>
        <label for="rowCount">Enter the number of rows:</label>
        <input type="number" id="rowCount" min="1" value="1">
    </div>

    <div>
        <label for="colCount">Enter the number of columns:</label>
        <input type="number" id="colCount" min="1" value="1">
    </div>

    <button onclick="generateTable()">Generate Table</button>

    <div id="tableContainer">
        <!-- The table will be appended here -->
    </div>

    <script>
        function generateTable() {
            // Get user input for rows and columns
            const rowCount = document.getElementById('rowCount').value;
            const colCount = document.getElementById('colCount').value;

            // Create a table element
            const table = document.createElement('table');

            // Create table rows and columns based on user input
            for (let i = 0; i < rowCount; i++) {
                const row = table.insertRow();

                for (let j = 0; j < colCount; j++) {
                    const cell = row.insertCell();
                    cell.textContent = `Row ${i + 1}, Col ${j + 1}`;
                }
            }

            // Append the table to the container in the DOM
            const tableContainer = document.getElementById('tableContainer');
            tableContainer.innerHTML = ''; // Clear previous content
            tableContainer.appendChild(table);
        }
    </script>

</body>
</html>

```
# 0utput
![Screenshot (77)](https://github.com/21002624/DOM/assets/113762183/1c8bcae3-7fc9-410d-9c49-195233e9b414)

