# Water Quality Analysis and Potability Monitoring | Power BI

An interactive Business Intelligence dashboard built with Microsoft Power BI to analyse water-quality measurements and compare potable and non-potable water samples.

## Project Overview

This project explores 3,276 water samples using data preparation, modelling, DAX calculations, and interactive visualizations. It transforms the raw dataset into an accessible dashboard for examining water-quality parameters and their relationship with the dataset's potability classification.

## Dataset

- **Dataset:** Water Potability Dataset
- **Records:** 3,276
- **Attributes:** 10
- **Potable samples:** 1,278
- **Non-potable samples:** 1,998
- **Potability percentage:** 39.01%

### Attributes

| Attribute | Description |
|---|---|
| `ph` | pH measurement |
| `Hardness` | Water hardness |
| `Solids` | Total dissolved solids |
| `Chloramines` | Chloramine concentration |
| `Sulfate` | Sulfate concentration |
| `Conductivity` | Electrical conductivity |
| `Organic_carbon` | Organic carbon measurement |
| `Trihalomethanes` | Trihalomethane measurement |
| `Turbidity` | Water turbidity |
| `Potability` | Dataset classification (0 = Not Potable, 1 = Potable) |

## Tools and Technologies

- Microsoft Power BI Desktop
- Power Query
- DAX (Data Analysis Expressions)
- SQL Server / SSMS
- Power BI Report Builder

## Data Preparation and Modelling

- Imported and inspected the dataset in Power BI.
- Used Power Query to examine missing values and prepare the data.
- Created cleaned fields: `ph_clean`, `Sulfate_clean`, and `Trihalomethanes_clean`.
- Created a `Potability_Status` lookup table.
- Established a relationship between the potability field in the main table and the lookup table.
- Created a `Water_Quality` classification column.

## Dashboard Features

- KPI cards for total, potable, and non-potable samples, and potability percentage.
- Donut chart showing potable versus non-potable sample distribution.
- Average parameter comparisons by water-quality category.
- 100% stacked column chart for potability distribution.
- Interactive slicer for Potable and Not Potable categories.

### Key Metrics

| KPI | Value |
|---|---:|
| Total Samples | 3,276 |
| Potable Samples | 1,278 |
| Non-Potable Samples | 1,998 |
| Potability Percentage | 39.01% |

## DAX Measures

The following examples show the measures used for the dashboard. Adjust table or column names if they differ in your Power BI file.

```dax
Total Samples =
COUNTROWS(water_potability)
```

```dax
Potable Samples =
CALCULATE(
    COUNTROWS(water_potability),
    water_potability[Potability] = 1
)
```

```dax
Non-Potable Samples =
CALCULATE(
    COUNTROWS(water_potability),
    water_potability[Potability] = 0
)
```

```dax
Potability Percentage =
DIVIDE(
    [Potable Samples],
    [Total Samples],
    0
) * 100
```

## Project Workflow

1. Import the water-potability dataset.
2. Inspect and prepare the data using Power Query.
3. Create cleaned columns for selected parameters.
4. Build the data model and lookup relationship.
5. Create calculated columns and DAX measures.
6. Design KPI cards and analytical charts.
7. Add slicers for interactive exploration.
8. Explore Row-Level Security and paginated reporting.

## Future Enhancements

- Machine-learning-based water-potability prediction.
- Advanced statistical and correlation analysis.
- Automated data refresh.
- Dynamic Row-Level Security.
- Cloud-based report publishing and sharing.

## Limitations

This project provides exploratory analysis of the supplied dataset. The visual comparisons do not establish that any individual parameter causes a sample to be potable or non-potable, and the dashboard is not a laboratory certification of drinking-water safety. Advanced features such as RLS and paginated reporting should be considered complete only after they have been configured and tested in the project environment.

## Conclusion

This project demonstrates how Business Intelligence techniques can transform water-quality data into interactive visual insights. It brings together data preparation, modelling, DAX calculations, and dashboard development to support exploration of water-quality measurements and potability classifications.
