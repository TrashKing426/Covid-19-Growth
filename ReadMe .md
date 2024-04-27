# Covid Growth Simulation

**Summary** 

In this project we seek to simulate the Covid epidemic spread across the globe and the populations that were affected more severly by the virus. 
We will be simulate it the spread of covid implementing a random walks and using the pandas package to import data recovered online from the [<u>John Hopkins University of Medicine](https://coronavirus.jhu.edu/data/animated-world-map)</u>, the [<u>CDC Covid Data Tracker](https://covid.cdc.gov/covid-data-tracker/#datatracker-home)</u>, the [<u> probability of covid-19 infection by a cough](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7976050/)</u>  (add others as you find them). We hope to accurately simulate the spread of the covid virus around the globe using pandas, numpy, and scipy python packages. Our goal is to find the speed and path of the virus as well as charting the rate of infection as it moves from country to country. Knowing that most disease outbreaks follow an exponential model, we can use the Monte Carlo method to find the area under the curve or the population infected out of the general population. We plan to generate a map of the continents and to simulate the spread with a random walk and testing the infection rate through interactions on a daily basis both with and without a mask. The Due to the high number of cases, and the large number of people on the planet, it is easiest to compute these many problems using a for loop to create a step counter. With this we can see who gets infected and where it is more likely to occur (country-wise). By creating this we hope to personally gain a better understanding of the computation behind pandemics, but to also gain the skill in distributing massive amounts of data into a realistic simulation. 


**Motivation**

 We know that the data used will span the timeframe of 01/22/2020 to 03/10/2023. While we know that the first cases of covid may have been reported before these dates in other countries, the cases were not being tracked as closely at the time. We aim to use a computational appraoch to find deviations in data sets. We know most diseases spread in an exponential fashion following the equation 
 $$
 \Delta N_d = E *p * N_d
$$

$$
  N_{d+1} = (1 + E * p)N_d
 $$

 where $N_d$ = Number of cases on a given day

  E = Average number of people an infected person is exposed to each day

  p = probability of each exposure becoming infection.

If we can expect the average of people the infected person to be within a certain and random range, we can implement the numpy package to find the range at which this average deviates
Code implemented will be incorporated from our Computational Physics class at CSULB, as well as data from the sites stated above. We use computation to find the changes in daily or other increments. With our data and the knowledge that epiemics grow exponentially, we can solve for the area under the curve using the Monte Carlo method. We can test to estimate the max number of cases to be expected and compare it to the max cases reported of a given day. We can then graph the spread of hte disease using this model as a random walk generator. 

**Results** 

for our computations, we will find the average range of people an infected person may be exposed to.
$E = \frac{\sum(x_1 + x_2 + ...+ x_n)}{N}$

[<u>the probability of infection has been estimated as follows](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7976050/)</u> :

first find the distribution of infected particles in cough/ sneeze cloud, where $U_c$ is the front velocity, $z$  is the axial coordinate, and $U_o$ and $d_c$ are reference velocity and length scalars 

$$
\frac{U_c}{U_o} = e^{-\frac{-4.763z}{d_c}}
$$

Convert the equation into a function of position and time
$$
t = \frac{d}{U_o}[e^{\frac{z}{d}-1}]
$$

Apply the Gaussian funtion as follows, where $U$ is the axial velocity, $r$ is the radial coordinate, and $b$ is the velocity width
$$
\frac{U}{U_c} = e^{-\frac{r^2}{b^2}}
$$

Flow rate of the croo-section
$$
C = \int_0^{\infty}2\pi UC_rd_r = \int_0^{\infty}2\pi U_ce^{-\frac{r^2}{b^2}}C_ce^{-\frac{r^2}{b^2}}rdr
$$

Amount of infected air breathed in by nearby person, $r_q$ is a measure of offset wrt to the axis of cough cloud where the person is located, $r_2 = r_1 + R$, and $t_b$ is the breathing time  ( about 2 seconds). $C_r$ is also a function of location ($r_1$ and z)
$$
C_r = \frac{\pi b^2U_cC_cft_b}{B}[e^{-\frac{Br_1^2}{b^2}}-e^{-\frac{Br_2^2}{b^2}}]
$$

B is a constant and f is the area fraction
$$
B = (1+\frac{b^2}{b_c^2}), f = \frac{\pi R^2}{\pi(r_2^2-r_1^2)}
$$

Normalize contaminated air with inhaled air, where Q is the colume of air coughed and $C_0$ is the exit concentration
$$
C_S = QC_0
$$

Quanta for infection
$$
\mu = \frac{C_R}{C_s}
$$

and finally the probability of infection
$$
p = 1-e^{-\mu}
$$

with this alone we know that we need to use compuation to pass through every person getting sick as this probabilty changes with regards to a person position and proximity. Other factors affect the infect, such as age, sex, and race which will be accounted for further on. As we move through the population and observe the restrictions that were put in place by different locations, we can see the spread slow or speed up. As we include more data through pandas, we can compare the simulations spread rate with real data to test our simulation is semi-accurate. 

**Questions**

questions we hope to answer with this simulation is 
1. What days experiences the greatest infection rate
2. Where and how did the infection spread across the globe over time
3. what country did it spread the fastest in
4. who was the most affected group to get sick
5. how far did the disease spread on average during the pandemic. 

```
# # formulas to use for code later
# N = 
# E = 
# p = 
# N_d = 
# dN_d = E * p * N_d
```

