# Modia
Modia is a domain specific extension of [Julia](http://julialang.org/ "Julia") for **modeling and simulation of physical systems**. The first version of Modia is planned to be uploaded in Summer 2017. An overview about Modia is given in a [paper](http://link.springer.com/chapter/10.1007%2F978-3-319-47169-3_15) on the [ISoLA conference 2016](http://www.isola-conference.org/isola2016/).

Modia is designed to model physical systems (electrical, mechanical, thermo-dynamical, etc.) that are made by differential and algebraic equations, that is expression=expression. An example is Newton's equation. Julia allows such a syntax and provides meta-programming to symbolically solve equations and JIT compile them. The authors used previous experience from the design of the modeling language [Modelica](https://www.modelica.org/). Modia will also be used to design and evaluate features for future Modelica versions.Component models are defined by @model macros. Such models contain definition of variables with various attributes such as start values, min, max, SI unit, etc. An @equations macro is used to define the equations of such a component. Coupling between components is expressed using a connect statement involving groups of variables. The semantics is either to constrain connected variables to be equal or to constrain a set of variables to sum to zero, for example to model Kirchhoff's current law. By these constructs it's possible and convenient to build models with hundred thousands of equations describing the dynamics of a car, an airplane, a power plant and others. Numeric solution is made by an extension to [Sundials IDA solver](http://computation.llnl.gov/projects/sundials/ida) with the KLU sparse matrix package.