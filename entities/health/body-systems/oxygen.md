# Oxygen

## Some data regarding oxygen consumption in the body.

At rest a human consumes about 250 ml of oxygen each minute, 4.16 mL per second, so approximately 4.16/22.4 = 0.18 mmol per second (22.4 is the molar volume of oxygen under 1 atm and 25 degree celsius). https://www.britannica.com/science/human-respiratory-system/Interplay-of-respiration-circulation-and-metabolism

* Average volume of a human body : 65 L https://bionumbers.hms.harvard.edu/bionumber.aspx?s=n\&v=3\&id=109718
* One milliliter of body then consume 0.18/65/1000 = approximately 2.77\*10^-6 millimoles per second. We'll call that **MilliMolesOfOxygenPerMillilitersOfBody**.

## Oxygen needs of individual body parts

A body part might, or might not, need oxygen. At the basis, it's the layers composing it that needs oxygen. Generally, the formula will be very simple, let's call L a single layer and O() the function for the needed oxygen. O(L) is expressed in millimoles, Vol(L) in milliliters and MilliMolesOfOxygenPerMillilitersOfBody is the constant above (unit in the name). The volume of a layer is currently simply the volume of its body part.

$$O(L) = \text{MilliMolesOfOxygenPerMillilitersOfBody} \times \text{Vol(L)}$$

Now for each layers present in the body part, we just compute the average of their need in oxygen to get the need of the bodypart itself.



## Oxygen reserve of individual body parts

The amount of oxygen a single body part can hold will rely on its volume and on a factor that user can pass in parameter.

$$R_o(B) = \text{MilliMolesOfOxygenPerMillilitersOfBody} \times \text{Vol(B)} \times \text{ReserveFactor}$$

The reserve factor is here to allow the user to set different amount of oxygen reserves for body parts, thus making some dying faster than others.



## Some data regarding blood and oxygen volume in a human

_The maximum volume of oxygen which the blood can carry when fully saturated is termed the oxygen carrying capacity, which, with a normal haemoglobin concentration, is approximately 20 mL oxygen per 100 mL blood._

{% embed url="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4666443/" %}

Of course, oxygen doesn't circulate in the body like in the air. In blood, it is densely packed into haemoglobin. We can safely consider that haemoglobin makes up 2% of blood volume, so oxygen is packed by a factor ten compared to normal atmospheric conditions.

Upon being taken in atmos by lungs, oxygen should turn into haemoglobin, so that there's no actualy oxygen into blood.
