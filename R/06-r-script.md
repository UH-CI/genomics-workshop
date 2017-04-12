#Usefulness of R scripts

Besides being an amazing interactive tool for data analysis, R software commands can also be executed as scripts. This is useful for example when we need to work in large projects where different parts of the project needs to be implemented using different languages that are later glued together to form the final product.

In addition, it is extremely useful to be able to take advantage of pipeline capabilities of the form
```
cat file.txt | preProcessInPython.py | runRmodel.R | formatOutput.sh > output.txt
```
and design your tasks following the Unix philosophy:

Write programs that do one thing and do it well. Write programs to work together. Write programs to handle text streams, because that is a universal interface. — Doug McIlroy


Basic R script

A basic template for an R script is given by

```
#! /usr/bin/env Rscript

# R commands here
```

To start with a simple example, create a file myscript.R and include the following code on it:

```
#! /usr/bin/env Rscript

x <- 5
print(x)
```

Now go to your terminal and type chmod +x myscript.R to give the file execution permission. Then, execute your first script by typing ./myscript.R on the terminal. You should see

```
[1] 5
```

displayed on your terminal since the result is by default directed to stdout. We could have written the output of x to a file instead, of course. In order to do this just replace the print(x) statement by some writing command, as for example


#Processing command-line arguments

To accept argument from the command line inside the script the following line will read the arguments into a variable.
```
args <- commandArgs(TRUE)
```

So if you call our script from the command line like so:
```
./myscript.R Ecoli_metadata.csv "My Title"
```
The args variable is a vector so to access the filename argument (Ecoli_metadata.csv) from the above we use:

```
filename <- args[1]
```
This assigns the first argument to the filename object. Now if we wanted to open that file we would use the following:
```
metadata <- read.csv(filename)
```
This would read the csv file we passed in as an argument to the metadata object.

So if we want to put together a script that reads a genome metadata csv file and outputs a plot as an image we would use the following in a script file:

```
#! /usr/bin/env Rscript
library(ggplot2)
args <- commandArgs(TRUE)
filename <- args[1]
metadata <- read.csv(filename)
genome_size <- metadata$genome_size
mygraph <-ggplot(metadata) +
  geom_point(aes(x = sample, y= genome_size, color = generation, shape = cit), size = rel(3.0)) +
  theme(axis.text.x = element_text(angle=45, hjust=1))
mygraph + ggtitle(args[2])
ggsave('genome_plot.png')
```

#Challenge

Use the command line to run an R script that reads the Ecoli_metadata.csv file to plot the metadata and creates a png file.

You on the UH ITS HPC you will need to load the R module prior to running the R script.

* What do you need to define tell the system this is a R script
*
