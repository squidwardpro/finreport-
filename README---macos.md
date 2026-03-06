## Generating the HTML Report From a File

The report generator works in two steps:

1. Read the contents of the report file.
2. Insert that content into the HTML template used for the report page.

This allows analysts to write their financial gap analysis in a simple text file and convert it into a browser-viewable report.

---

## Step 1 — Capture the Report File Contents

Run the following command in your terminal to read the contents of the report file located in the user's downloads directory.

```bash
REPORT_CONTENT=$(cat ~/downloads/report.txt)
```

This command:

* uses `cat` to read the file located at:

```
~/downloads/report.txt
```

* stores the full contents of the file inside a variable called:

```
REPORT_CONTENT
```

---

## Step 2 — Generate the HTML Report

Next, generate the HTML report and insert the captured file contents inside the `<body>` tag.

```bash
echo "<html>
<body>

$REPORT_CONTENT

</body>
</html>" > report.html
```

This command creates a new file called:

```
report.html
```

and inserts the contents of `/downloads/report.txt` into the body of the HTML document.

---

## Result

If the file:

```
~/downloads/report.txt
```

contains:

```
Financial Gap Analysis Report

Asset: AMZN
Previous Close: 174.22
Open Price: 180.15
Gap: +3.40%

Volume Spike: Yes
Internal Notes:
Gap triggered by overnight macroeconomic data release.
```

The generated `report.html` file will contain:

```html
<html>
<body>

Financial Gap Analysis Report

Asset: AMZN
Previous Close: 174.22
Open Price: 180.15
Gap: +3.40%

Volume Spike: Yes
Internal Notes:
Gap triggered by overnight macroeconomic data release.

</body>
</html>
```

You can then open the generated report in your browser:

```bash
open report.html
```

From there, the report can be exported or captured as an image for internal financial analysis documentation.
