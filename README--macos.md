## Generating the HTML Report From a File

The report generator works in two steps:

1. Read the contents of the report file.
2. Insert that content into the HTML template used for the report page.

This allows analysts to write their financial gap analysis in a simple text file and convert it into a browser-viewable report.

---

## Step 1 — Capture the Report File Contents

Run the following command in your terminal to read the contents of the report file and store it in a variable.

```bash
REPORT_CONTENT=$(cat report.txt)
```

This command:

* uses `cat` to read `report.txt`
* stores the full contents of the file in a variable called `REPORT_CONTENT`

---

## Step 2 — Generate the HTML Report

Next, generate the HTML report and insert the file contents inside the `<body>` tag.

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

and inserts the contents of `report.txt` into the body of the HTML document.

---

## Result

If `report.txt` contains:

```
Financial Gap Analysis Report

Asset: NVDA
Previous Close: 720.45
Open Price: 742.10
Gap: +3.01%

Volume Spike: Yes
Internal Notes:
Detected cross-exchange price discrepancy during pre-market session.
```

The generated HTML file will look like this:

```html
<html>
<body>

Financial Gap Analysis Report

Asset: NVDA
Previous Close: 720.45
Open Price: 742.10
Gap: +3.01%

Volume Spike: Yes
Internal Notes:
Detected cross-exchange price discrepancy during pre-market session.

</body>
</html>
```

You can then open the report in a browser:

```bash
open report.html
```

or capture an image of the rendered report for internal documentation.
