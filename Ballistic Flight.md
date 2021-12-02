# Ballistic Flight
When you are in space, the ballistic flight is the quickest and probably the deadliest way to get planetside. It is the simplest trajectory to describe, but also features the highest decelerations and thermal loads.

## Index
1. [[Ballistic Flight#Equations of motion|Equations of Motion]]
2. [[Ballistic Flight#Flight path|Flight Path]]
3. [[Ballistic Flight#Traversed distance|Traversed Distance]]
4. [[Ballistic Flight#Altitude-velocity profile|Altitude-velocity profile]]
5. [[Ballistic Flight#Maximum deceleration|Maximum Deceleration]]
6. [[Ballistic Flight#Thermal loads|Thermal Loads]]


## Equations of motion
To start deriving useful properties about the ballistic flight, first set up [[The Sketch]] and derive the three accompanying equations of motion:
![[the_sketch.png]]

Corresponding equations of motion are:
$$ m \dfrac{dV}{dt} = - D - mg \sin(\gamma) $$
$$ mV \dfrac{d\gamma}{dt} = L - mg \cos({\gamma}) \left( 1 - \dfrac{V^2}{gR} \right) = L - mg \cos({\gamma}) \left( 1 - \dfrac{V^2}{V_c^2} \right) $$
$$ \dfrac{dR}{dt} = \dfrac{dh}{dt} = V \sin(\gamma) $$


## Flight path
We start off our derivations by making these equations of motion a bit simpler with some assumptions that are only valid for the ballistic flight (and so not for the gliding or skipping trajectories). First, since we're essentially just ditching into the atmosphere like a rock, without any care for aerodynamics, we will assume that the vehicle will not generate any lift.

```ad-warning
title: Assumption 1
color: 200,80,225

We assume that the vehicle **will not generate any lift** during the entry -> $L = 0$.
```

It turns out that this means that we can also ignore the mass, as it divides out. The second equation of motion now looks like:
$$ mV \dfrac{d\gamma}{dt} = 0 - mg \cos({\gamma}) \left( 1 - \dfrac{V^2}{V_c^2} \right) $$
$$ V \dfrac{d\gamma}{dt} = - g \cos({\gamma}) \left( 1 - \dfrac{V^2}{V_c^2} \right) $$

Now instead of looking at $t$ as the independant variable, we look at $h$ and try to write the second equation of motion as if we were differentiating with respect to $h$. For this, we will need a compatibility equation to write $d\gamma/dh$ in terms of $d\gamma/dh$. We can do this with the help of the third equation of motion:
$$\dfrac{d\gamma}{dt} = \dfrac{d\gamma}{dh} \dfrac{dh}{dt} = V \sin(\gamma) \dfrac{d\gamma}{dh}$$

This we can use to reduce the second equation of motion to:
$$ \tan(\gamma) \dfrac{d\gamma}{dh} = - \dfrac{g}{V^2} $$

```ad-note
title: Math
icon: paperclip
collapse: close
color: 180,180,180

Given
$$ V \dfrac{d\gamma}{dt} = - g \cos({\gamma}) \left( 1 - \dfrac{V^2}{V_c^2} \right) $$
and
$$\dfrac{d\gamma}{dt} = V \sin(\gamma) \dfrac{d\gamma}{dh}$$

we can substitute the latter into the former:

$$ V \left( V \sin(\gamma) \dfrac{d\gamma}{dh} \right) = - g \cos({\gamma}) \left( 1 - \dfrac{V^2}{V_c^2} \right) $$
$$ V^2 \sin(\gamma) \dfrac{d\gamma}{dh}  = - g \cos({\gamma}) \left( 1 - \dfrac{V^2}{V_c^2} \right) $$
$$ \dfrac{\sin(\gamma)}{\cos(\gamma)} \dfrac{d\gamma}{dh}  = - \dfrac{g}{V^2}\left( 1 - \dfrac{V^2}{V_c^2} \right) $$
$$ \tan(\gamma) \dfrac{d\gamma}{dh}  = - \dfrac{g}{V^2}\left( 1 - \left( \dfrac{V}{V_c} \right)^2 \right) $$

Now we assume that the velocity $V$ will be substantially smaller than the local circular velocity $V_c$. 

~~~ad-warning
title: Assumption
color: 200,80,225

We assume that the instantaneous velocity is much smaller than the local circular velocity, i.e: $$ V \ll V_c $$
~~~

If this is the case, then the fraction $V/V_c$ will be small, and thus its square will be quite close to zero. As such, we ignore it, and the above becomes:

$$ \tan(\gamma) \dfrac{d\gamma}{dh}  = - \dfrac{g}{V^2}$$
```

Now we recognise that for the analysis that will follow, we're mainly interested in the early, hypersonic section of the entry trajectory, because this is where the largest largest mechanical and thermal loads occur. For this, we assume that the instantaneous velocity $V^2$ is very high, orders of magnitude above that of $g$.

```ad-warning
title: Assumption 2
color: 200,80,225

We assume that the vehicle travels so fast that over short timespans, gravity has very little effect on its flight path. As such:
$$V^2 \gg g$$
```

This assumption implies that the flight path for the early, hypersonic section of the flight is rectilinear, as gravity is not able to bend it very much. This means that the flight path angle changes relatively little during this time, especially when the flight path angle $\gamma$ is relatively large. And so we assume a constant flight path angle for this section of the flight.

```ad-warning
title: Assumption 3
color: 200,80,225

We assume that when the vehicle travels at very high speeds, the flight path is rectilinear. Therefore:
$$\dfrac{d\gamma}{dh} \approx 0 $$
```

## Traversed distance
Because we assume the flight path of a ballistic entry to be rectilinear, especially during the early sections, it is very straightforward to calculate the traversed path. It can simply be approximated by a triangle of height $h$, provided the base of the triangle is straight. We assume therefore that the Earth's surface underneath is flat.

```ad-warning
title: Assumption 4
color: 200,80,225

We assume that the Earth's surface is flat.
```

The traversed distance $d$ can then simply be computed using simple trigonometry:
$$\tan| \gamma | = \dfrac{h}{d}$$
$$ d = \dfrac{h}{\tan| \gamma | }$$

## Altitude-velocity profile
To derive the 


## Maximum deceleration

## Thermal loads

