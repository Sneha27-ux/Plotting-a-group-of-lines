1. The script(plot_lines.R) reads tsv data from "stdin" making it flexible for various input data sources (files or pipelines).
2. The input data is structured with an X column (independent variable), a Y column (dependent variable), and a category column that represents different groups or series to be plotted.
3. The script uses aes(color = Category, group = Category) in the ggplot call, which automatically plots separate lines for each unique value in the category column. This makes it handling any number of categories in the data, allowing for the visualization of multiple lines in the same plot.
4. The script accepts command-line arguments for the output file name, x-axis label, y-axis label, and plot title. This makes it versatile.
5. By using geom_line(), the script draws a line plot for each Category, ensuring that each line is distinguished by color. This approach is well-suited for visualizing trends or comparisons among different groups in the data
6. The use of theme_minimal() gives the plot a clean and modern appearance.
7. As long as the input format (X, Y, and Category columns) is consistent, the script can handle different data sizes, from small datasets to large ones with many points and categories. The plotting logic will automatically adjust based on the unique values in the Category column.
8. Finally to plot the graph, use linux terminal and plot_lines.R.
   
cat data/q2_data.tsv | Rscript plot_lines.R "different_clusters.png" "Relative from center [bp]" "Enrichment over Mean" "MNase fragment profile"

