# Molecular Dynamics Gas Compressibility

I wrote this in Mathematica for a physical chemistry lab, to work out how real gases deviate from ideal behavior using molecular dynamics simulation data.

The notebook pulls in the pooled simulation output from the class, filters and sorts it, then computes the compressibility factor Z for each gas, temperature, and density. From there it builds quasi-isotherms at 10, 200, and 400 K and compares the 400 K results against NIST data. The main finding is that the deviations follow the noble gas order He < Ne < Ar < Kr < Xe, which is what you'd expect from London dispersion forces getting stronger with size. The most ideal case in the set was argon at 100 mol/m3 and 800 K (Z = 1.00078), the most negative deviation was argon at 20,000 mol/m3 and 10 K (Z = 0.38675), and the most positive was argon at 35,000 mol/m3 and 1000 K (Z = 2.55949).

The simulation data is pooled output from the class, the analysis is mine.

Open Lab2PostLabHernanVallejo.nb in Mathematica and run it. It imports the data from Wolfram Cloud, so you'll need a connection.
