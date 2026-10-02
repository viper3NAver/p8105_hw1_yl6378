Homework 1
================
yl6378

## Problem 1

``` r
data("penguins", package = "palmerpenguins")
```

The penguins dataset contains measurements of penguins from the Palmer
Archipelago in Antarctica. It has 344 rows and 8 columns. Important
variables include species (Adelie, Chinstrap, Gentoo), island (Biscoe,
Dream, Torgersen), bill length and depth (mm), flipper length (mm), body
mass (g), sex, and year.

The mean flipper length is 200.92 mm, excluding missing values.

``` r
penguin_plot = ggplot(
  penguins,
  aes(x = bill_length_mm, y = flipper_length_mm, color = species)
) +
  geom_point(na.rm = TRUE) +
  labs(
    title = "Flipper length versus bill length",
    x = "Bill length (mm)",
    y = "Flipper length (mm)",
    color = "Species"
  )

penguin_plot
```

![](hw1-data-science_files/figure-gfm/penguin-scatterplot-1.png)<!-- -->

``` r
ggsave(
  filename = "penguin_scatterplot.png",
  plot = penguin_plot,
  width = 7,
  height = 5,
  units = "in",
  dpi = 300
)
```

The scatterplot shows the relationship between bill length and flipper
length, with different colors representing the three penguin species.
Penguins with missing measurements are omitted from the plot.
