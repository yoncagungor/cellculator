# Cellculator <a name="cellculator"></a> 

> Cellculator uses the raw viable and dead cell counts from the hemocytometer directly to calculate the viability and viable cell density.
> Cellculator can process multiple data at once. 
> 

[![DOI:10.1002/0471142956.cya03as00](http://img.shields.io/badge/DOI-10.1002/0471142956.cya03as00-B31B1B.svg)](https://doi.org/10.1002/0471142956.cya03as00)

## Contents

- [Calculating Viable Cell Density](#viable_cell_density_calculation)
- [Calculating Cell Viability](#calculating_cell_viability)
- [Basic Cellculator Commands](#basic_cellculator_commands)

 
## Calculating Viable Cell Density<a name="viable_cell_density_calculation"></a> 
[[back to top]](#cellculator)
  
> Viable cell density is calculated by cellculator using the below equation:


  ![Formula](https://rightbrainedscientist.files.wordpress.com/2015/11/cellcounttotal.jpg)
    


## Calculating Cell Viability<a name="calculating_cell_viability"></a> 
[[back to top]](#cellculator)

> Cell viability is the ratio of viable cells divided by the total number of cells.

viable cells
------------ x 100 = viability %
total count

## Basic Cellculator Commands<a name="basic_cellculator_commands"></a> 
[[back to top]](#cellculator)
| **Command** | **Description** |
| --- | --- |
| `cc vcd` | Gives the list of all *viable cell counts*. |
| `cc viab` | Gives the list of *viability* of all cells that were counted. |
