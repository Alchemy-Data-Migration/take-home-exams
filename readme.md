Task: Debug the CSV file loading issue

You are given a web page that is supposed to display the contents of a CSV file with 1000 rows. The page is using JavaScript to load the file and parse its contents, but there are several bugs that are causing the data to not be displayed correctly. Your task is to find and fix all of these bugs.

The HTML and JavaScript code for the page is provided below.

<!DOCTYPE html>
<html>
  <head>
    <title>CSV Data</title>
  </head>
  <body>
    <table id="data-table"></table>
    <script>
      const dataTable = document.getElementById('data-table');

      fetch('data.csv')
        .then(res => res.text())
        .then(data => {
          const rows = data.split('\n');
          for (const row of rows) {
            const cells = row.split(',');
            const tr = document.createElement('tr');
            for (const cell of cells) {
              const td = document.createElement('td');
              td.textContent = cell;
              tr.appendChild(td);
            }
            dataTable.appendChild(tr);
          }
        });
    </script>
  </body>
</html>
