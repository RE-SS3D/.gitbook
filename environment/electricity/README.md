# ⚡ Electricity

The power system will be the backbone system which connects objects throughout the station together to the electrical system. It’s primary purpose is to be a link between objects which produce power and objects which consume power, as well as abstracting away the complexity of power generation and consumption off of the individual producers and consumers to simplify their implementation and give the designers more flexibility with systems.

The power system will additionally be responsible for the events related to power, such as when a component's power is lost or when it is reconnected. At any time a power consuming or producing object will be able to easily access the electrical information such as available watt’s (or joules per second).

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption><p>Figure 1) Power system overview</p></figcaption></figure>

## Terminology & Physics <img src="https://lh3.googleusercontent.com/Gu82RVgvMEJshQ79i0fFAW66sFtgTQLpF0AfwWAyR1F3l7HRUfMEF4FfTpmX8vjrk_9rxG7ehL-0jjHLnOS2A6S8CC0wLM7EWRi5OGGk5-j8qg-7am-LlKL4CxpPE6MiTQBYwsnmByIs66rAcKTFVw" alt="" data-size="line">

The physics implementation has been partially inspired by a popular simulation game, Oxygen Not Included (ONI). You can find a brief description of the power system in ONI [here](https://oxygennotincluded.fandom.com/wiki/Guide/Power\_Circuits).

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption><p>Figure 2) Power in ONI</p></figcaption></figure>

The power system will be described electrically with two components, Watts and Joules. The relationship between them is:

$$
Watts = Joules/Time
$$

In other words, 60W = 60J/s. Watts and joules are different physically speaking, a joule is a measure of energy (or work) used when doing something, and a watt is a measure of how many joules you are using over time (Joules / s). If your microwave says it uses 900 watts then it is consuming 900 joules per second to heat up your microwave dinner. Therefore we can describe electrical relationships really simply and effectively, for example a 60 watt light bulb operated for an hour will use 60J \* 3600s = 360kJof energy.

## Power System <img src="https://lh3.googleusercontent.com/Gu82RVgvMEJshQ79i0fFAW66sFtgTQLpF0AfwWAyR1F3l7HRUfMEF4FfTpmX8vjrk_9rxG7ehL-0jjHLnOS2A6S8CC0wLM7EWRi5OGGk5-j8qg-7am-LlKL4CxpPE6MiTQBYwsnmByIs66rAcKTFVw" alt="" data-size="line">

The power system will consist of any amount of circuits which allow the connection of producers and consumers, the circuit will be made up of continuous wires and optionally Area Power Controllers (APC’s), an APC is a special object which connects to a wire on one side and allows for the wireless connection of energy consuming components to the electrical circuit.

The electrical wires will be able to be damaged, repaired, cut, and reconnected. If a wire is damaged too much it will become cut, a player or script can also cut wires. When a wire is cut or reconnected the circuit/s will be updated and refreshed. All objects on a circuit are instantaneously and logically connected to one another, the entire circuit is one logical object and has some given wattage based on its producers and consumers.

The station will be made of several circuits which logically separate objects based on geography and power consumption, circuits can be subdivided through objects such as transformers or other objects. A transformer will allow for a high wattage circuit to be subdivided to a low wattage circuit (i.e. a 2000W circuit connected to several 500W circuits)
