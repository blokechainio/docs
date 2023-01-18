---
description: A vehicle needed to participate in the race
---

# 🌄 Cruiseship

## 🚀 Cruiseship

### NFTs Specification

| **Utility** | Participating in the race to become one of the first validators in the Blokechain.                           |
| ----------- | ------------------------------------------------------------------------------------------------------------ |
| **Supply**  | Not greater than 9000                                                                                        |
| **Minting** | Free mint with any Access Key NFT after the start of the race.                                               |
| **Buying**  | On the secondary market only, after the start of the race.                                                   |
| **Selling** | At any time after the start of the race on the secondary market (with the loss of the achieved race result). |
| **Burning** | When finishing at Blokechain.                                                                                |

### The Physics of The Flight

Each cruiseship produced in our shipyard is equipped with an engine that creates artificial inertia in a given direction. Units of energy called Energons are constantly expended to maintain it. If they are not spent on maintaining speed, the artificial inertia will begin to decrease until the ship loses it entirely and stops. The greater the speed of the cruiseship, the more Energons will be spent per unit of time to maintain it.

The main task of the pilot is to determine the hourly consumption of Energons. You can manually change this parameter at any time. The ship will begin to accelerate or decelerate accordingly until it reaches the speed that requires the specified amount of Energons per hour. Afterward, the cruiseship will maintain this speed until the pilot changes the Energon consumption or runs entirely out of Energons.

The _**Engine Efficiency**_ parameter determines how productively the Energons are used. The higher the parameter, the fewer Energons are needed to maintain the same speed, or the faster the ship will fly with the same consumption of Energons. Depends on the key type. The parameter can only be improved by burning additional keys.

The _**Inertia Retention**_ parameter affects how fast your cruiseship will lose its artificial inertia. Though all the ships will lose it in 25 hours, the speed of losing it differs depending on the Inertia Retention value. The higher the parameter is, the slower your ship will slow down. Depends on the time of possession of the cruiseship during the prelunch phase. The parameter can be further increased by burning additional keys having Inertia Retention greater than 0.

Both parameters of the ship can be improved temporarily with the in-game boosters or permanently with additional keys burning.

### Prelaunch Catapult

When you get a ship at the prelaunch stage, an electromagnetic catapult is used to launch it - you immediately start moving towards Blokechain by inertia. The cruiseship cannot lose this real, not artificial, inertia. So when the ship is launched using an electromagnetic catapult, it does not fully stop when it loses its artificial inertia but continues to move with speed acquired by the primary acceleration.

After each launch, the electromagnetic catapult loses its power, and each subsequent launch will accelerate the ships less. After the start of the space race, all participants will start on their own, and their initial real inertia will be zero. This means that when they lose artificial inertia, they will stop completely.

Thus, the earlier you will burn the key, the farther from the Earth you will be when the space race officially starts, and the more kilometers will separate you from the majority of participants. Moreover, even if you run out of Energons during the race, you will still continue to move towards the finish, though at a relatively low speed.

### Cruiseship Upgrade

By burning additional keys, you can improve the ship's parameters at any moment - during the prelaunch stage and after the race has already started. The parameters of the keys are added to the ship's parameters.

There is a special bonus for burning 4 different types of keys (A, B, C, D) to improve one ship. When a cruiseship is upgraded with all four types of keys, 20 points will be added to both parameters.

### The Economy of The Flight

In the Pioneer Program, we decided to recreate the Blokechain tokenomics without simplifications to test it in real-life conditions before launching the blockchain. The only things we changed for the space race were to reduce the number of tokens to 100 000 and slightly accelerate the timing of the issuance.

Therefore, the relationship of Astonite -> Cosmogrinder -> Energon fully corresponds to the BKG-> Grinder -> BKC in Blokechain tokenomics.

**Astonite Mining**

A unique mineral called Astonite is needed to obtain Energons. You can receive it during daily minigame tournaments. Unfortunately, the amount of Astonite is not only limited in the Universe but also constantly decreasing.

Astonite can be obtained in daily tournaments on the game "Astonite Mining." The event is held simultaneously for all participants. Astonite is distributed according to the tournament score. The tournament launch time will be shifted each day by one hour so that all pioneers will be in identical conditions.

These tournaments are the crucial mechanism to protect against multi-accounts. Since the competition will not last long (about 5-10 minutes) and will require all the player's attention, there will be no practical possibility of playing simultaneously from multiple accounts. And, of course, we will make it impossible to create a bot that can play instead of a human.

**Obtaining Energons**

Energons are obtained by recycling Astonite in a unique device called a "cosmogrinder." The higher the conversion rate - the harder it is for the cosmogrinder to proceed. That is why cosmogrinder will work faster if you offer less Energon for one Astonite.

### Appendix

#### Energon Consumption

The hourly consumption of Energons depending on the speed and the _**Engine Efficiency**_ (EE) parameter is calculated by the formula:

$$
Energons=\frac{Speed^{4}}{EE\cdot10^{17}}
$$

#### Inertia Leakage

The cruiseship will lose all artificial inertia if there are no Energons left in 25 hours no matter what. The _**Inertia Retention**_ (IR) parameter affects the speed of the leakage. The percent of the speed remaining is calculated by the formula:

$$
Speed=\frac{100+\left(IR+1\right)}{1+\frac{0.16*hour^{2}}{IR+1}}-\left(IR+1\right)
$$

#### Acceleration and deceleration

When a pilot sets a new Energon Consumption rate the cruiseship changes its speed.

If the new value is higher, the ship starts to accelerate linearly so that it will achieve a new speed in one hour.

If the new value is lower, the vessel stops the engine and will continue moving by inertia until the speed reaches the value required for the specified consumption level.

#### Prelaunch Catapult

The first launch will give the cruiseship a speed of 15 000 km/hour. Every next launch will be less effective. The catapult power for a particular launch can be calculated by the formula:

$$
Speed=\frac{1500000}{N+100}
$$
