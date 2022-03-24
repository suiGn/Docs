Techniques for art.

# CRAFTING AND RECORDING SOUND.

***SUI GN***

<!--ModernChurch studio theory, processes and methods.-->

***Chapters:***

Understanding Effect Pedals:

- Their types and flow in the chain.

- The Effects Loop.

Mixing:

- Decibels.
- Gain Staging.

Cables: in writings...

# Understanding effect pedals, 

##### Their type and flow in the chain.

- **Modulation Type:**
  Definition: Waveform manipulation.
  Things like chorus, tremolo, univibe, vibrato, phaser, flanger.
  Modulation itself is not an effect. Rather, it’s the process by which an effect is produced.
  - Before ambient effects (time-altering effects like delay or echo)
  - After distortion and gain-impacting effects

**Ambient or a “timed” effect:**

- Reverbs.

- Delays.

  If the reverb is first, the delay will work on the trails left by the reverb.
  Delay first and the reverb is a traditional way and is ok.
  No rules about what goes first.
  Both ways could sound good and are just experimentation.

**Output Buffers: **
Buffers create impedance firewalls.
In the end, output buffer to avoid trouble...

**Impedance-Sensitive Pedals:**

**Dynamic Pedals (Can go after DIST/OD):**
These are things that rely on or adjust the guitar tone's dynamics.
Compressors, Filters, envelope filters, octave pedals. (Early on the guitar chain). 
Close to the guitar, they depend on the dynamic of the guitar to trigger what they do.
Get them early on the chain so they are more responsive to the dynamics on the guitar (After the buffer pedal).

**Distortion devices.**
Overdrive devices = Soft clip.
distortion devices = Hard Clip.

Order of Distortion does not matter if you are not stacking devices.
But if you are going to stack, High gain pedals closer to the guitar.
High gain before low gain pedals when stacking.

**Eq before the Boost.**

**Volume pedals:**
Closer to the amp far from the guitar.
If you use it after other pedals, is going to act like a master volume. 
Early on the chain could as well adjust the volume from your guitar knob and get the same result so it would be redundant to have it first in the chain.
If you decide to use it early on the chain, it will adjust the volume of what goes into the pedals. It could change tone saturation going in other pedals (if that's what you are looking for).

### Benefits to be gained when using an effects loop:

-  Effects placed in the loop tend to sound clearer and more pronounced.
-  There is less likelihood of any signal loss due to an impedance mismatch.

Effects loop does have its negatives as well.
- Need to run extra cables to use it
- Extra cable length for the loop can change your signal.

**What effects should you put in the loop?**

- Modulation

- Time-based effects. 

  Pedals like **chorus, tremolo, delay and reverb** sound better in the effects loop. 

  Boosts, Dirt effects: Distortion, overdrive, and compressors work best in front of the amp.



***Pedal Flow in front of the amp:***

Running all the chains to the front of the amp without going to the effect loop.

```flow
st=>start: Guitar
impedenceGroup=>operation: Impedence-Sensitive Pedals
inputBuffer=>operation: Input Buffer
dynamicGroup=>operation: Dynamic Pedals
distorGroup=>operation: Distorions / Overdrive Pedals
eqBoostGroups=>operation: EQ / Boost Pedals
modGroup=>operation: Modulation Pedals
timeGroup=>operation: Time-Based and Ambient Pedals.
end=>end: Front Amp
st->impedenceGroup->inputBuffer->dynamicGroup->distorGroup->eqBoostGroups->modGroup->timeGroup->end


```



*** Pedal Flow for Effect Loop ***

Run modulation, Time Based, and Ambient Pedals through the effect loop.

PREAMP OUT is equivalent to SEND in some amps.

POWER AMP IN is equivalent to RECEIVE in some amps.

Preamp out or Send, goes into the input of the first pedal that will run through the effect loop, then it chain pedals and the output of the last one goes to RECEIVE or Power AMP IN.

```sequence

Amp Send/Receive->Pedals: Send to Pedal Input
Pedals-->Amp Send/Receive: Output Pedal to Receive

```

[^Cables]: The greater the distance in cabling, the greater the loss in signal power due to cable resistance. Bring signal back up to acceptable levels when long chains.

# Mixing:

***Decibels***:

A decibel is a logarithmic unit. A logarithm is a power or exponent to which we raise a certain number - or base.

An exponential change in power is perceived as a linear change in loudness.

When dealing with sound, the base is always 10 since the decibel is, by definition, a base 10 logarithm.

There is a distinction between ***loudness, intensity, and power.***

***Loudness*** is a perception of the strength of a signal. ***Intensity or power*** is measurable entities. Power is the amount of energy generated or dissipated per unit of time. It is measured in joules per second.

***Power*** is usually given in ***watts.***
$$
W = E / T
$$

> where W = Power (in watts), E = Energy (in joules), T = Time (in seconds)


$$
1 W = 1 J/s
$$

> 1 Watt = 1 Joule per second.

***Power*** is the amount of work that is being done by something.

***Power*** is energy exerted over time.

***Sound*** ***energy*** produces ***power***.

***Intensity*** is a measure of the amount of energy in a specific area in one second.

Amount of sound power over a given area.
$$
I = W / S
$$

> where I = intensity, W = Power (in watts) and S = surface area (in m2)

**Gain Staging**

“adjusting the level at each point of amplification to ensure an optimal signal-to-noise ratio, without unwanted distortion”
Make sure the audio is set to an optimal level for the next processor in the chain to minimize noise and distortion

In the analog world, gain staging refers to adjusting the level at each point of amplification to ensure an optimal signal-to-noise ratio, without unusable distortion. 

You need a buffer or safety zone that can accommodate transient spikes or loud moments without causing horrible distortion. This is headroom. 

dBFS means “decibels full scale,” and it describes the highest possible level in the digital world you can achieve without harsh digital clipping


**What is Unity Gain?**

When passing audio through a piece of gear, if the output level is the same as when the device is not in the signal path, “unity gain” has been achieved — input equals output, level-wise. You put one volt in, you get one volt out, which is said to equal a gain of one or “unity.”

-
