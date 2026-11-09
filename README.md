# How Real Gases Depart From Ideal Behaviour

## Read this first: what Z means

Z is the compressibility factor, Z = PV/RT. It compares a real gas with an ideal gas at the same temperature and density. Z = 1 means the gas behaves ideally. Below 1, molecules attract each other more than they repel, so the pressure is lower than ideal. Above 1, repulsion dominates, so the pressure is higher than ideal. Every Z value below is on that scale.

I ran the simulations and wrote all the analysis code in this repo, including the filtering, sorting, Z calculation, and comparison code.

## The numbers, with their limits

Within these five gases at these conditions, deviation from ideal behaviour increases in the order He < Ne < Ar < Kr < Xe. That ordering applies to the temperatures and densities tested here. It does not hold everywhere: at low density and high temperature, all gases approach Z = 1.

The three most extreme Z values in the dataset, all for argon, are:

- Most ideal: argon at 100 mol/m3 and 800 K, Z = 1.00078
- Most negative deviation: argon at 20,000 mol/m3 and 10 K, Z = 0.38675
- Most positive deviation: argon at 35,000 mol/m3 and 1000 K, Z = 2.55949

## How temperature is handled

The plots use quasi-isotherms at nominal 10, 200, and 400 K. A quasi-isotherm is a near-constant-temperature slice taken from constant-energy runs, so the temperature drifts within each slice and no flat transition appears. The underlying dataset covers a wider range, up to 1000 K, which is why individual Z values are cited at 800 K and 1000 K even though the plotted quasi-isotherms are at 10, 200, and 400 K. The 400 K quasi-isotherm is the one compared against NIST reference data, using Mathematica's `ThermodynamicData` function to calculate molar density at each pressure.

## Reproduce it

Open `md-gas-compressibility.nb` in Mathematica and evaluate it from the first cell to the last. It loads the simulation output from Wolfram Cloud, so you'll need a connection.

You should get the same Z tables, the same quasi-isotherm plots at 10, 200, and 400 K, and the same 400 K NIST comparison.

Sample output (argon):

| Density (mol/m3) | Temperature (K) | Z |
|---:|---:|---:|
| 100 | 800 | 1.00078 |
| 20,000 | 10 | 0.38675 |
| 35,000 | 1000 | 2.55949 |

## Files

- `md-gas-compressibility.nb` — the analysis notebook
- `README.md` — this file

Code in this repo is under the MIT licence.
