# Staking

### Overview

* Helm is inflationary via staking
* The max stake length is 8400 days (23 years)
* Stakes can be started, ended on time, ended early, ended late, and deferred
* Every 4 years since genesis, a Big Pay Day occurs, meaning 2x staking amplifier on that day

### Inflation

Inflation is paid to stakers for minting new tokens through staking. The rate of inflation is fixed to φ, the golden ratio. Apart from the first 2 years since the genesis of Helm, which allows users to mint Helm by locking up XEN Crypto and earn bonus rewards, the only way to produce more Helm is with staking.

$$
inflationRate = 1.618033988749894848
$$

Inflationary rewards are compounded as a result of your Helm stake size.

$$
inflation = helm * (1 + \dfrac{inflationRate}{100})^\frac{term}{365 
days}
$$

###

### Started

time bonus

$$
\tau=1 + (\dfrac{term}{8400})
$$

size bonus

$$
\sigma=1 - (\dfrac{1}{helm + 1})
$$

total bonus

$$
\beta = \sigma * e^{(\tau)}
$$

### Ended

#### on time

#### early

$$
\epsilon=\left(\dfrac{blockTs - stakeTs}{term}\right)^2
$$

#### late

$$
\lambda=1 - \left(\dfrac{lateDays}{180 days}\right)^3
$$

### Deferred

