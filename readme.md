Task: Debug the CSV file loading issue

You are given a web page that is supposed to display the contents of a CSV file with 1000 rows. The page is using JavaScript to load the file and parse its contents, but there are several bugs that are causing the data to not be displayed correctly. Your task is to find and fix all of these bugs.

The HTML and JavaScript code for the page is provided below.

```
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
```


To run the code, you can follow these steps:

Save the HTML and JavaScript code in a file named "index.html" on your computer.
Download the CSV file and save it in the same directory as the HTML file.
Open the HTML file in a web browser. The browser will execute the JavaScript code, which will fetch the CSV file, parse its contents, and display the data in a table on the page.
You may need to install a web server on your computer to run the code, as some browsers block fetch requests to local files for security reasons. Alternatively, you can upload the HTML and CSV files to a web server and access the HTML file through a URL.

If you are having trouble running the code, make sure that you have saved the files with the correct names and in the correct locations. You should also check the console in your web browser for any error messages, which can help you identify any issues with the code.
