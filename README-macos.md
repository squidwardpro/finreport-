v## Generate a Report Using a Terminal Command

You can generate the report HTML directly from the terminal by reading the contents of a file and inserting it into the HTML template.

This works by using `cat` to read the file and redirect the output into the HTML structure.

### Command

Run the following command in your terminal:

```
(echo "<html><body>"; cat report.txt; echo "</body></html>") > report.html
```

### What This Does

1. `echo "<html><body>"`
   Starts the HTML document.

2. `cat report.txt`
   Reads the contents of the report file.

3. `echo "</body></html>"`
   Closes the HTML document.

4. `> report.html`
   Writes the combined output into a new HTML file.

### Example

If `report.txt` contains:

```
Financial Gap Analysis Report

Asset: TSLA
Previous Close: 198.12
Open Price: 205.44
Gap: +3.69%

Volume Spike: Yes
Notes:
Large overnight movement detected across multiple exchanges.
```

Running the command will produce `report.html` containing:

```
<html>
<body>

Financial Gap Analysis Report

Asset: TSLA
Previous Close: 198.12
Open Price: 205.44
Gap: +3.69%

Volume Spike: Yes
Notes:
Large overnight movement detected across multiple exchanges.

</body>
</html>
```

You can then open the generated report in a browser:

```
open report.html
```

or convert it to an image for internal documentation.
