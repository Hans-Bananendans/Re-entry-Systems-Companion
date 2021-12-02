# Derivation of the exponential atmosphere model

To derive the exponential atmosphere model, we start with the assumption that the atmosphere is an _ideal gas_. 
```ad-warning
title: Assumption 1
color: 200,80,225

We assume the atmosphere is an **ideal gas**.
```

Doing so allows us to use the ideal gas law, which can be formulated as follows:
$$p = \rho R T = \rho \frac{R^*}{M}T$$
where:
-	$R = R^*/M$	is the gas constant for air [$J/kg K$]
-	$R^*$ is the universal gas constant: $8314.32$ [$J/kmol K$]
-	$M$ is the molecular mass of the atmosphere [$kg/kmol$]

In general, the gas constant for air, the blend of gases found at sea level in Earth's atmosphere, equals 287 [$J/kg K$]. So we have an equation with which we can relate pressure, density, and temperature. But what about altitude? To relate altitude to the aforementioned parameters, we will use the hydrostatic equation. However, when we do so, we must assume that the Earth's atmosphere is in hydrostatic equilibrium.

```ad-warning
title: Assumption 2
color: 200,80,225

We assume the atmosphere is in **hydrostatic equilibrium**.
```

Using the hydrostatic equation, we can relate changes in pressure to changes in altitude:
$$dp = -\rho g dh$$

We wish to integrate this, so we can get an explicit expression. However, when we do so, we need to know how the density $\rho$ and the gravitation acceleration $g$ change as a function of $h$. In regards to the gravitational acceleration, we can introduce a geopotential altitude $z$, which is related to $h$ according to:
$$g_0 dz = g dh$$

Where $g_0$ is the gravitational acceleration at the surface of the Earth, where $h=0$. We can prove that when we are just a few hundred kilometers above the Earth's surface, it can be reasonably assumed that $z\approx h$. 

```ad-note
title: Proof: For Low Earth Orbits, $z \approx h$
icon: paperclip
collapse: close
color: 180,180,180

For any spheroid, we can write that the local gravity is inversely proportional to the square of the distance from the point from which it is is acting. Thus, we can relate $g$ and $g_0$ as follows:
$$ g_0 R_e^2 = g (R_e+h)^2$$
This can be rewritten as:
$$ g = g_0 \dfrac{R_e^2}{(R_e+h)^2} = \dfrac{g_0}{\left(1+\dfrac{h}{R_e}\right)^2}$$

We can substitude this in the equation given earlier:
$$ g_0 dz = g dh = \dfrac{g_0}{\left(1+\dfrac{h}{R_e}\right)^2} dh $$

We can now integrate this equation. The left hand we integrate from $0$ to $z$, whilst we integrate the right hand side from $0$ to $h$:

$$ \int^z_0 dz^* = \int^h_0 \dfrac{1}{\left(1+\dfrac{h^*}{R_e}\right)^2} dh^*$$

The left hand side can be reworked to a slightly easier to integrate form:
$$ \dfrac{1}{\left(1+\dfrac{h^*}{R_e}\right)^2} = \dfrac{1}{\left(\dfrac{1}{R_E}\left(R_E+h^*\right)\right)^2} = \dfrac{1}{\dfrac{1}{R_E^2}\left(R_E+h^*\right)^2} = \dfrac{R_E^2}{\left(R_E+h^*\right)^2} $$

Reintroducing this to the original integral, we can solve it:
$$ \int^z_0 dz^* = \int^h_0 \dfrac{R_E^2}{\left(R_E+h^*\right)^2} dh^*$$
$$ \int^z_0 \dfrac{1}{R_E} dz^* = \int^h_0 \dfrac{R_E}{\left(R_E+h^*\right)^2} dh^* $$
$$ \dfrac{z}{R_E} = 1- \dfrac{R_E}{R_E+h} =  \dfrac{R_E+h}{R_E+h} - \dfrac{R_E}{R_E+h}= \dfrac{h}{R_E+h} $$
$$ \dfrac{z}{R_E} = \dfrac{h}{R_E} \left( \dfrac{1}{1+\dfrac{h}{R_E}}\right) \approx \dfrac{h}{R_E} \left( 1 - \dfrac{h}{R_E} \right) $$
$$ z = h \left( 1 - \dfrac{h}{R_E} \right) $$

For Low Earth Orbits, for example at 400 km altitude, the ratio $h/R_E$ is approximately 0.06, which means that $z\approx h$ to within ~$6\%$. So if we assume that we are within a few hundred kilometers from the Earth's surface, we can assume that $z\approx h$, and we will only be a few percent off.
```

```ad-warning
title: Assumption 3
color: 200,80,225

Since the Earth's atmosphere extends only a few hundred kilometers above the Earth's surface (Karman line is at 100 km), we will assume that $z \approx h$.
```

Combining the ideal gas law, the hydrostatic equation, and the relation between $h$ and $z$, we can derive the following:
$$p = \rho R T \quad ; \quad dp = -\rho g dh \quad ; \quad g_0 dz = g dh $$
$$ \dfrac{dp}{p} = \dfrac{-\rho g dh}{\rho R T} = -\dfrac{g}{R T} dh = -\dfrac{g_0}{R T} dz $$

To continue, we would like to integrate. However, if we were to integrate now, we would need expressions for $T$, $\rho$, and $g$ as function of $h$. So in order to progress, we will assume that we have an isothermal atmosphere, which means that the temperature is constant with altitude, and that the gravitational acceleration is also constant with altitude.

```ad-warning
title: Assumptions 4 and 5
color: 200,80,225

We assume an **isothermal atmosphere** -> $\dfrac{dT}{dh} = 0$.
We assume **constant gravitational acceleration** -> $g = g_0$
```

Now we can continue from the previous equation:
$$ \dfrac{dp}{p} = -\dfrac{g}{R T} dh $$
$$ dp = -\dfrac{p g}{R T} dh = -\dfrac{(\rho R T) g_0}{R T} dh = -\rho g_0 dh $$
Since we have assumed that we have an isothermal atmosphere, we know that $T$ will not vary with altitude. In addition, $R$ is a constant. So when the altitude is varied, the change in pressure will only be due to a change in density:
$$ dp = R T d\rho$$
So we can equate this to what we had previously:
$$ -\rho g_0 dh = R T d\rho$$
$$ \dfrac{d\rho}{\rho} = - \dfrac{g_0}{R T} dh$$

This can be integrated:
$$ \int^{\rho}_{\rho_0} \dfrac{d\rho^*}{\rho^*} = - \int^h_0 \dfrac{g_0}{R T} dh^* $$

$$ \ln (\rho) - \ln(\rho_0) = \ln\left(\dfrac{\rho}{\rho_0}\right) = - \dfrac{g_0}{R T} h $$

We will now introduce the definition of the quantities $\beta$ and the scale height $H_s$:
$$\beta = \dfrac{g_0}{RT} \quad ; \quad H_s = \dfrac{1}{\beta} = \dfrac{RT}{g_0}$$

Using this definition, we can write the previous equation as follows:
$$ \ln\left(\dfrac{\rho}{\rho_0}\right) = - \beta h $$
$$ \dfrac{\rho}{\rho_0} = e^{-\beta h} = e^{-\dfrac{h}{H_s}}$$

Given that we've assumed the ideal gas law to be valid, and we've assumed an isothermal atmosphere, this also means that:
$$ \dfrac{\rho}{\rho_0} = \dfrac{\dfrac{p}{RT}}{\dfrac{p_0}{RT_0}} = \dfrac{p}{p_0} = e^{-\beta h} = e^{-\dfrac{h}{H_s}}$$

A few notes on the quality of the model: This is a very basic atmospheric model. Some of the assumptions we've made here, particularly the isothermal atmosphere assumption, really cement the notion that this model is not to be used for anything other than preliminary analyses. For more refined answers, there are standardized atmosphere models available, such as _GRAM_ or _NRLMSISE-00_.