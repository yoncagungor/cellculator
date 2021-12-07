# Cellculator <a name="cellculator"></a> 

> Cellculator uses the raw viable and dead cell counts from the hemocytometer directly to calculate the viability and total viable cell counts. It also calculates the cell suspension volume for the new passages.
> Cellculator can process multiple data at once. 
> 

[![DOI:10.1002/0471142956.cya03as00](http://img.shields.io/badge/DOI-10.1002/0471142956.cya03as00-B31B1B.svg)](https://doi.org/10.1002/0471142956.cya03as00)

## Contents

- [Calculating Total Viable Cell Counts](#viable_cell_counts_calculation)
- [Calculating Cell Viability](#calculating_cell_viability)
- [Calculating Seeding Volume](#seeding)
- [Basic Cellculator Commands](#basic_cellculator_commands)

## Calculating Total Viable Cell Counts<a name="viable_cell_counts_calculation"></a> 
[[back to top]](#cellculator)
  
> Cellculator can calculate the number of living cells simultaneously from the raw data taken directly from a hemocytometer. 

Calculations are based on the below equation:

  ![Formula](https://rightbrainedscientist.files.wordpress.com/2015/11/cellcounttotal.jpg)
    
Cellculator assumes that # of squares equal to 5, df equals to 2 and the volume (ml) is equal to 30 if not specified.


To specify these variables, please check out the [*commands section*](#basic_cellculator_commands).

## Calculating Cell Viability<a name="calculating_cell_viability"></a> 
[[back to top]](#cellculator)

> Cell viability is calculated by taking the ratio of viable cell numbers to the total number of cells.

Cellculator needs both living and dead cell numbers to calculate the viability. The output is given as %.
Cellculator uses the below equation to calculate cell viability:

(Viable cell number / Total cell number) x 100 = Viability %

## Calculating Seeding Volume <a name="seeding"></a> 

> Seeding volume is calculated from the viable cell density data using the below equation:



## Basic Cellculator Commands<a name="basic_cellculator_commands"></a> 
[[back to top]](#cellculator)

| **Command** | **Description** |
| ----------- | --------------- |
| `cc vcc` | Gives the list of all *viable cell counts*. |
| `cc via` | Gives the list of *viability* of all cells that were counted. |


### 1. Viable Cell Counts: `cc vcc`

>The `cc vcc` command has three variables that should be specified if they are different than their predetermined values.

| **Options** | **Descriptions** | **Predetermined Values** |
| :-----------: | --------------- | :--------------------:|
| `sq` | Squares that counted to take the raw data from the hemocytometer. | 5 |
| `df` | Dilution factor that is used to prepare the cell suspension sample. | 2 |
| `ml` | Volume of the total cell suspension in the flask. | 30 |


Sample code:

`cc vcc -sq 5 ; -df 2 ; -ml 30 hemocytometer_counts.csv` 

The code written above gives all of the actual living cell numbers in the 30 ml cell suspension as a list. Since the `sq`, `df` and `ml` options are predetermined, the code given below will give the same output:

`cc vcc hemocytometer_counts.csv`

If different number of squares are counted or the dilution factor is different, it should be specified with the `sq` and `df` options respectively. 

The file should include the cell name, viable and dead cells counted in the hemocytometer.

### 2. Viability: `cc via`

> The `cc via` command does not have any options. It will calculate the viability once the viable and dead cell counts counted in the hemocytometer are indicated.

Sample code:

`cc via hemocytometer_counts.csv`

This command will give the list of viabilities of all cell suspensions at once.

### 3. Seeding: `cc sd`

> The `cc sd` command works with the output of the `cc vcc` command. It basically calculates the volume of cells needed for the seeding at a specified density to a specified volume.
> The seeding density is specified with the `dn` variable and the the final volume of the cell suspension after seeding is specified with `vol` variable. 

Sample code:

`cc vcc hemocytometer_counts.csv > actual_counts.txt`

`cc sd -dn 0,2 ; vol 30 actual_counts.txt`

This code will give the volume of cell suspension needed for seeding at **0,2 mm/ml** in a final volume of **30 ml** for the cell passage.
