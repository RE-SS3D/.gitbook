# Power Grid

## Circuits <img src="https://lh3.googleusercontent.com/Gu82RVgvMEJshQ79i0fFAW66sFtgTQLpF0AfwWAyR1F3l7HRUfMEF4FfTpmX8vjrk_9rxG7ehL-0jjHLnOS2A6S8CC0wLM7EWRi5OGGk5-j8qg-7am-LlKL4CxpPE6MiTQBYwsnmByIs66rAcKTFVw" alt="" data-size="line">

Circuits allow objects to be logically connected together, a circuit does not necessarily need to be powered, it’s main function is connecting objects together across the station. For example a circuit could connect a collection of solar panels together to a Solar Panel Controller (SPC), the solar panels themselves do not actually generate watts, however by being connected to the SPC via a circuit the SPC can then itself output watts onto another circuit.

Circuits will be physically connected together via wires, however they can also be connected together logically if it’s required, for example the lights in a room might be apart of a circuit in the room but do not have literal wires reaching to them, and are instead connected “through the air” to a junction box which is physically connected to wires. The actual implementation of deciding what objects should connect to what APCs, and how it should interact with the player is not a part of the immediate scope of this proposal, only the immediate functionality of the APC is being considered here.

## Switches & Intermediate Objects <img src="https://lh3.googleusercontent.com/Gu82RVgvMEJshQ79i0fFAW66sFtgTQLpF0AfwWAyR1F3l7HRUfMEF4FfTpmX8vjrk_9rxG7ehL-0jjHLnOS2A6S8CC0wLM7EWRi5OGGk5-j8qg-7am-LlKL4CxpPE6MiTQBYwsnmByIs66rAcKTFVw" alt="" data-size="line">

Switches are one example of an object which can be used to separate two circuits, the object itself only allows each circuit to be connected to one another when it is engaged. For this reason it must be easy to logically connect circuits together via links such as switches.

## Producers <img src="https://lh3.googleusercontent.com/Gu82RVgvMEJshQ79i0fFAW66sFtgTQLpF0AfwWAyR1F3l7HRUfMEF4FfTpmX8vjrk_9rxG7ehL-0jjHLnOS2A6S8CC0wLM7EWRi5OGGk5-j8qg-7am-LlKL4CxpPE6MiTQBYwsnmByIs66rAcKTFVw" alt="" data-size="line">

A producer is responsible for putting some wattage of power onto the circuit it is directly connected to, an example of a producer is a Solar Panel Controller (SPC), which itself will be connected to multiple solar panels. However in the actual implementation the solar panels themselves will be the energy producers. But for the sake of the example the SPC could produce a different wattage depending on how many solar panels it is connected to, and the direction of the solar panels.

Objects will be able to quickly and easily query information about its circuit, such as the amount of connected solar panels through a function such as: connectedCircuit.GetAllOfType\<SolarPanel>()

## Consumers <img src="https://lh3.googleusercontent.com/Gu82RVgvMEJshQ79i0fFAW66sFtgTQLpF0AfwWAyR1F3l7HRUfMEF4FfTpmX8vjrk_9rxG7ehL-0jjHLnOS2A6S8CC0wLM7EWRi5OGGk5-j8qg-7am-LlKL4CxpPE6MiTQBYwsnmByIs66rAcKTFVw" alt="" data-size="line">

A consumer will have some wattage of power it requires to operate, for example a light might need 10W of power to operate, and if it doesn’t receive more than 10J/s of energy it will fail and start flickering, then after a moment it will turn off completely until it receives power again.

Consumers on a circuit share the energy on the circuit, if a circuit has 100W of power available, each object on that circuit will reduce the available watts, if the circuit has two lights which each consume 10W then the energy available decreases to 80W (80J/s).

## Batteries <img src="https://lh3.googleusercontent.com/Gu82RVgvMEJshQ79i0fFAW66sFtgTQLpF0AfwWAyR1F3l7HRUfMEF4FfTpmX8vjrk_9rxG7ehL-0jjHLnOS2A6S8CC0wLM7EWRi5OGGk5-j8qg-7am-LlKL4CxpPE6MiTQBYwsnmByIs66rAcKTFVw" alt="" data-size="line">

A battery is a special object, it is both a consumer and a producer in one. When the battery's connected circuit has excess power, for example a 100W circuit with 80W free, it will consume the excess power up to its wattage intake. A battery for example may be able to consume 200W of energy, but in this case it only has 80W available. Unlike other consumers the battery does not fail when its  actual energy intake is under its required intake (200W). The battery then converts the watts into energy which is stored internally, for example a battery might store 10kJ of energy.

When the intake wattage becomes negative, for example maybe the power goes off and our two lights are now on a circuit with -20W, the battery switches from a consumer to a producer, it uses its internally stored 10kJ of energy and puts it onto the circuit. The battery will output as much power per second as is required to keep all the components on the circuit powered, if the circuit requires 20W the battery will output 20W, at this rate the battery is consuming 20J/s of its stored energy and will use its entire 10kJ of storage in 1000 seconds.

## Event Order <img src="https://lh3.googleusercontent.com/Gu82RVgvMEJshQ79i0fFAW66sFtgTQLpF0AfwWAyR1F3l7HRUfMEF4FfTpmX8vjrk_9rxG7ehL-0jjHLnOS2A6S8CC0wLM7EWRi5OGGk5-j8qg-7am-LlKL4CxpPE6MiTQBYwsnmByIs66rAcKTFVw" alt="" data-size="line">

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption><p>Figure 3) Proposed circuit event order</p></figcaption></figure>
