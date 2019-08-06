---
Style: Post
Title: Power Query Excel.Workbook Function
---

[Excel.Workbook](https://docs.microsoft.com/en-us/powerquery-m/excel-workbook)

## Syntax
Excel.Workbook(workbook as binary, optional useHeaders as nullable logical, optional delayTypes as nullable logical) as table

## Return value
Returns a record of Sheets from the Excel workbook.

## Example
Excel.Workbook(File.Contents([Folder Path]&[Name]), true, true)


The second parameter of Exce.Workbook() "useHeaders" is to decide if headers will be prompted automatically. It is nullable and when the value is null it means false, i.e. the headers will not be used.

Regarding the third parameter, please see an artical from Chris Webb at <https://blog.crossjoin.co.uk/2019/02/02/excel-workbook-and-the-delaytypes-option-in-power-query-power-bi/>

>"Originally, Excel.Workbook used to read the entire workbook data to accurately assign types to the columns. This was EXTREMELY slow on large workbooks."

So, the third parameter "delayTypes" is used to delay the type assigning behavior. According to Chris, Setting delayTypes to true results in much better performance.

delayTypes is nullable and is set to be false by default if not specified.

