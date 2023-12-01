# Misc. UI Elements

Other interfaces may also exist for more specific use cases, like using station consoles, changing settings on a pressure valve, or interacting with a player’s PDA. These exist in the form of windows that can be dragged around the screen for convenience, and often share similar design elements with each other.

Most of those might be achieved by implementing proper windows. Windows are UI elements opened when interacting with certain environment items, like accessing the terminal or a piece of tech that is not detailed enough on the level of its model/texture. Most windows should be interactable, movable and closable.

For a set of design guidelines one should take a look at 2D section of the art guide (LINK HERE)

### Composite Elements

Some UI elements can have variants to be switched for one another in case of different circumstances. In that case the variant switch needs to be seamless, meaning that the images for those elements need to be of the same size and with the same base position.

<figure><img src="https://lh3.googleusercontent.com/Lu3vp2XXXPZvDTKGgYPix5GX9UhHVfTpAhYi0Vmi48K7Gwa-3VuAMWFctu-gBv5y-mFzcg6c2OFQNm1eCGom4QVKcwiY1LqbDKzy62-8Qw0rEBP_GzpiDLI1cYPvI-OkJV6vsZj-Utmm" alt=""><figcaption><p>Thermometer variant files</p></figcaption></figure>

<figure><img src="https://lh5.googleusercontent.com/yO9sMV6n9unzCek8BqNpn_QlL3eWhadkX6re-iBbN00z4pxWl4LphPtAWWY9vXBmT-M7wrGcW4gKebWhehi40Tts9f5bYAaz4p6NmCifbWyVISVFVmK4L7ouUy3K-SMsr1tA-AW2VQb0" alt=""><figcaption><p>Thermometer variants’ concept.</p></figcaption></figure>

Note the bar, it is missing from the variant files themselves, but can be added within unity and be programmably extended or shrunk from the bottom of the thermometer.

UI elements can also consist of several parts to be layered on top of each other and programmed to be moved, colored or otherwise changed separately.

As an example, the atmospheric pressure meter consists of 3 parts: the base with a dial, the arrow to rotate and indicate the overall pressure on the base’s dial and an exclamation mark, to be colored and/or flashing in case of dangerous atmospheric conditions. The text for the exact atm amounts is added within Unity, using accepted project fonts, so it can also be changed programmably.

<figure><img src="https://lh3.googleusercontent.com/pz4QFbIqss7BPcPDDMG8YcP-XXAIHDzVsr-cS9IE48Ir7gPmxvBsxzN0ANijv947vcr32a4Bj-YgaIUp7RP9IS6_d69fjVwnHk9MqiDf5A4E-evrRCR0nxodT2EEO0USqSbabVSAgM8V" alt=""><figcaption><p>Pictured: the ATM sensor UI element in 3 parts and the preview of them put together.</p></figcaption></figure>

Same principle applies to the target dummy, surgery dummy and other complex UI elements.

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption><p>Pictured: several examples of complex composite UI elements.</p></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/vLY8OTZOhWBLj1gW0yNgCkVX2DBAchLmhXmWGJMLZWhF0XhHW8rDY6iTNb5Wfnzu5KwkYN-HfamlrTEN5LNjnmDtoqRHtkFhQBwAsf61JMShJmhyukAIO-GPevTPfxoPQZ_t6rGRLpzH" alt=""><figcaption><p>Pictured: a collection of layers for said elements. Note that the according naming of each part should be indicative and consistent within each element.</p></figcaption></figure>

!
