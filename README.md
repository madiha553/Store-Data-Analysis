# Store-Data-Analysis
This Analysis tells you about business performance of Store data which I break down into 3 parts.

1. Main KPI View – High-Level Business Summary

This page is designed to give an immediate snapshot of overall business health. Every visual here answers a “big-picture” question.

✅ KPI Cards

Total Revenue

Total Target

Target Achievement %

Total Profit

Total Orders

Active Customers

These cards give the audience a quick read of performance without needing to explore the details. The trendlines inside each card help viewers understand not just the final number, but how performance has been moving over time.

📈 Total Revenue Over the Period (Line Chart)

This visual tracks revenue month-by-month.
I added this because it:

shows seasonality or sudden peaks/drops,

highlights growth patterns,

and helps identify which months contribute the most.

This is usually the first visual decision-makers look at because it tells the story of performance over time.

📊 Revenue vs Target Table (Detailed View)

This table breaks down:

Monthly Target

Forecast

Actual Quantity Sold

MoM% changes

YTD Revenue

MTD

This is where operational teams look to understand whether targets are realistic, where gaps exist, and which months are over- or under-performing.
I included it because it provides clarity behind the KPIs and supports deeper analysis.

2. Product View – Understanding Product-Level Performance

This page focuses entirely on product categories, profitability, and customer return behavior.

🥧 Product Price Tier Distribution (Donut Chart)

Shows how many products fall into Low, Mid, and High price tiers.
This tells us:

which pricing segment dominates the catalog,

where the majority of sales volume likely comes from,

and how pricing strategy may influence revenue.

📊 Target Achievement Over the Period (Combo Chart)

This visual overlays:

Total Revenue

Revenue Target

Target Achievement %

The combination helps identify:

months where revenue exceeded targets,

periods where performance dipped,

and how consistent target achievement has been overall.

📉 Average Return Rate (%) by Product (Bar Chart)

I added this to highlight which products have higher return behavior.
This tells the business:

where quality issues may exist,

which items may need redesign or discontinuation,

and where operational cost is rising due to returns.

Products with unusually high returns stand out immediately here.

💵 Total Profit by Product (Bar Chart)

This chart ranks products based on profitability, helping answer:

Which products are the top revenue drivers?

Which items bring the highest margins?

Do high return-rate products also bring high profit?

It’s a great visual for category managers and finance teams to focus on top contributors.

3. Customer View – Understanding Customer Behavior

This section explores customer-level performance, demographics, and geographic contribution.

👤 Customer Revenue Table

Shows:

Total Revenue per customer

Revenue SPLY (Same Period Last Year)

Growth %

This helps identify:

high-value customers,

customers whose revenue is declining,

customers showing strong positive growth.

It’s extremely useful for retention planning and segmenting customers based on performance.

🗺️ Total Revenue by State & City (Map Visual)

This map is added to show:

geographic concentration of revenue,

regions with strong customer presence,

or areas with potential expansion opportunities.

The size of bubbles quickly communicates which regions bring the most business.

📊 Customers by Age Bins (Bar Chart)

This helps us understand customer demographics.
It answers:

which age groups dominate the customer base,

whether the brand appeals more to younger or older customers,

and how to shape marketing strategy.

Age segmentation is key for targeted campaigns.

This dashboard gives you a complete 360° view of business performance—from overall revenue to product outcomes and customer behavior.

M Language for Region Wise Forecast VS Target:
let
    Source = Excel.Workbook(File.Contents("C:\Users\CC\Downloads\PowerQuery Task 2 Part 1.xlsx"), null, true),
    #"Region Wise Forecast vs Target_Sheet" = Source{[Item="Region Wise Forecast vs Target",Kind="Sheet"]}[Data],
    #"Promoted Headers" = Table.PromoteHeaders(#"Region Wise Forecast vs Target_Sheet", [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"Region wise Year wise Forecast Vs Target", type any}, {"Column2", type text}, {"Column3", type any}, {"Column4", type any}, {"Column5", type any}, {"Column6", type any}, {"Column7", type any}, {"Column8", type any}, {"Column9", type any}, {"Column10", type any}, {"Column11", type any}, {"Column12", type any}, {"Column13", type any}, {"Column14", type any}, {"Column15", type any}, {"Column16", type any}, {"Column17", type any}, {"Column18", type any}, {"Column19", type any}, {"Column20", type any}, {"Column21", type any}, {"Column22", type any}, {"Column23", type any}, {"Column24", type any}, {"Column25", type any}, {"Column26", type any}, {"Column27", type any}, {"Column28", type any}, {"Column29", type any}, {"Column30", type any}, {"Column31", type any}, {"Column32", type any}, {"Column33", type any}, {"Column34", type any}, {"Column35", type any}, {"Column36", type any}, {"Column37", type any}, {"Column38", type any}, {"Column39", type any}, {"Column40", type any}, {"Column41", type any}, {"Column42", type any}, {"Column43", type any}, {"Column44", type any}, {"Column45", type any}, {"Column46", type any}, {"Column47", type any}, {"Column48", type any}, {"Column49", type any}, {"Column50", type any}}),
    #"Removed Blank Rows" = Table.SelectRows(#"Changed Type", each not List.IsEmpty(List.RemoveMatchingItems(Record.FieldValues(_), {"", null}))),
    #"Transposed Table" = Table.Transpose(#"Removed Blank Rows"),
    #"Merged Columns" = Table.CombineColumns(Table.TransformColumnTypes(#"Transposed Table", {{"Column2", type text}}, "en-US"),{"Column1", "Column2", "Column3"},Combiner.CombineTextByDelimiter(",", QuoteStyle.None),"Merged"),
    #"Transposed Table1" = Table.Transpose(#"Merged Columns"),
    #"Removed Columns" = Table.RemoveColumns(#"Transposed Table1",{"Column1"}),
    #"Promoted Headers1" = Table.PromoteHeaders(#"Removed Columns", [PromoteAllScalars=true]),
    #"Changed Type1" = Table.TransformColumnTypes(#"Promoted Headers1",{{",,Region", type text}, {"Forecast,1997,Dec", Int64.Type}, {"Forecast,1997,Nov", Int64.Type}, {"Forecast,1997,Oct", Int64.Type}, {"Forecast,1997,Sep", Int64.Type}, {"Forecast,1997,Aug", Int64.Type}, {"Forecast,1997,Jul", Int64.Type}, {"Forecast,1997,Jun", Int64.Type}, {"Forecast,1997,May", Int64.Type}, {"Forecast,1997,Apr", Int64.Type}, {"Forecast,1997,Mar", Int64.Type}, {"Forecast,1997,Feb", Int64.Type}, {"Forecast,1997,Jan", Int64.Type}, {"Target,1997,Dec", Int64.Type}, {"Target,1997,Nov", Int64.Type}, {"Target,1997,Oct", Int64.Type}, {"Target,1997,Sep", Int64.Type}, {"Target,1997,Aug", Int64.Type}, {"Target,1997,Jul", Int64.Type}, {"Target,1997,Jun", Int64.Type}, {"Target,1997,May", Int64.Type}, {"Target,1997,Apr", Int64.Type}, {"Target,1997,Mar", Int64.Type}, {"Target,1997,Feb", Int64.Type}, {"Target,1997,Jan", Int64.Type}, {"Forecast,1998,Dec", Int64.Type}, {"Forecast,1998,Nov", Int64.Type}, {"Forecast,1998,Oct", Int64.Type}, {"Forecast,1998,Sep", Int64.Type}, {"Forecast,1998,Aug", Int64.Type}, {"Forecast,1998,Jul", Int64.Type}, {"Forecast,1998,Jun", Int64.Type}, {"Forecast,1998,May", Int64.Type}, {"Forecast,1998,Apr", Int64.Type}, {"Forecast,1998,Mar", Int64.Type}, {"Forecast,1998,Feb", Int64.Type}, {"Forecast,1998,Jan", Int64.Type}, {"Target,1998,Dec", Int64.Type}, {"Target,1998,Nov", Int64.Type}, {"Target,1998,Oct", Int64.Type}, {"Target,1998,Sep", Int64.Type}, {"Target,1998,Aug", Int64.Type}, {"Target,1998,Jul", Int64.Type}, {"Target,1998,Jun", Int64.Type}, {"Target,1998,May", Int64.Type}, {"Target,1998,Apr", Int64.Type}, {"Target,1998,Mar", Int64.Type}, {"Target,1998,Feb", Int64.Type}, {"Target,1998,Jan", Int64.Type}}),
    #"Unpivoted Other Columns" = Table.UnpivotOtherColumns(#"Changed Type1", {",,Region"}, "Attribute", "Value"),
    #"Split Column by Delimiter" = Table.SplitColumn(#"Unpivoted Other Columns", "Attribute", Splitter.SplitTextByDelimiter(",", QuoteStyle.Csv), {"Attribute.1", "Attribute.2", "Attribute.3"}),
    #"Changed Type2" = Table.TransformColumnTypes(#"Split Column by Delimiter",{{"Attribute.1", type text}, {"Attribute.2", Int64.Type}, {"Attribute.3", type text}}),
    #"Reordered Columns" = Table.ReorderColumns(#"Changed Type2",{",,Region", "Attribute.2", "Attribute.3", "Attribute.1", "Value"}),
    #"Pivoted Column" = Table.Pivot(#"Reordered Columns", List.Distinct(#"Reordered Columns"[Attribute.1]), "Attribute.1", "Value"),
    #"Renamed Columns" = Table.RenameColumns(#"Pivoted Column",{{",,Region", "Region"}, {"Attribute.2", "Year"}, {"Attribute.3", "Month"}})
in
    #"Renamed Columns"

M language For Year Wise Forecast VS Targated
let
    Source = Excel.Workbook(File.Contents("C:\Users\CC\Downloads\PowerQuery Task 2 Part 1.xlsx"), null, true),
    #"Year Wise Forecast vs Target_Sheet" = Source{[Item="Year Wise Forecast vs Target",Kind="Sheet"]}[Data],
    #"Promoted Headers" = Table.PromoteHeaders(#"Year Wise Forecast vs Target_Sheet", [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"Year Wise Forecast Vs Target", type any}, {"Column2", type any}, {"Column3", type any}, {"Column4", type any}, {"Column5", type any}, {"Column6", type any}, {"Column7", type any}, {"Column8", type any}, {"Column9", type any}, {"Column10", type any}, {"Column11", type any}, {"Column12", type any}, {"Column13", type any}, {"Column14", type any}, {"Column15", type any}, {"Column16", type any}, {"Column17", type any}, {"Column18", type any}, {"Column19", type any}, {"Column20", type any}, {"Column21", type any}, {"Column22", type any}, {"Column23", type any}, {"Column24", type any}, {"Column25", type any}, {"Column26", type any}}),
    #"Removed Blank Rows" = Table.SelectRows(#"Changed Type", each not List.IsEmpty(List.RemoveMatchingItems(Record.FieldValues(_), {"", null}))),
    #"Transposed Table" = Table.Transpose(#"Removed Blank Rows"),
    #"Removed Blank Rows1" = Table.SelectRows(#"Transposed Table", each not List.IsEmpty(List.RemoveMatchingItems(Record.FieldValues(_), {"", null}))),
    #"Merged Columns" = Table.CombineColumns(#"Removed Blank Rows1",{"Column1", "Column2"},Combiner.CombineTextByDelimiter(",", QuoteStyle.None),"Merged"),
    #"Transposed Table1" = Table.Transpose(#"Merged Columns"),
    #"Promoted Headers1" = Table.PromoteHeaders(#"Transposed Table1", [PromoteAllScalars=true]),
    #"Changed Type1" = Table.TransformColumnTypes(#"Promoted Headers1",{{",Year", Int64.Type}, {"Forecast,Dec", Int64.Type}, {"Forecast,Nov", Int64.Type}, {"Forecast,Oct", Int64.Type}, {"Forecast,Sep", Int64.Type}, {"Forecast,Aug", Int64.Type}, {"Forecast,Jul", Int64.Type}, {"Forecast,Jun", Int64.Type}, {"Forecast,May", Int64.Type}, {"Forecast,Apr", Int64.Type}, {"Forecast,Mar", Int64.Type}, {"Forecast,Feb", Int64.Type}, {"Forecast,Jan", Int64.Type}, {"Target,Dec", Int64.Type}, {"Target,Nov", Int64.Type}, {"Target,Oct", Int64.Type}, {"Target,Sep", Int64.Type}, {"Target,Aug", Int64.Type}, {"Target,Jul", Int64.Type}, {"Target,Jun", Int64.Type}, {"Target,May", Int64.Type}, {"Target,Apr", Int64.Type}, {"Target,Mar", Int64.Type}, {"Target,Feb", Int64.Type}, {"Target,Jan", Int64.Type}}),
    #"Unpivoted Other Columns" = Table.UnpivotOtherColumns(#"Changed Type1", {",Year"}, "Attribute", "Value"),
    #"Split Column by Delimiter" = Table.SplitColumn(#"Unpivoted Other Columns", "Attribute", Splitter.SplitTextByDelimiter(",", QuoteStyle.Csv), {"Attribute.1", "Attribute.2"}),
    #"Changed Type2" = Table.TransformColumnTypes(#"Split Column by Delimiter",{{"Attribute.1", type text}, {"Attribute.2", type text}}),
    #"Pivoted Column" = Table.Pivot(#"Changed Type2", List.Distinct(#"Changed Type2"[Attribute.1]), "Attribute.1", "Value", List.Sum),
    #"Renamed Columns" = Table.RenameColumns(#"Pivoted Column",{{",Year", "Year"}, {"Attribute.2", "Month"}})
in
    #"Renamed Columns"
