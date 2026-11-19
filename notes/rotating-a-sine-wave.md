# When does a rotated sine wave stop falling?

I pictured a wave running from the third quadrant to the first. Viewed along its tilted centerline, it would still look like a sine wave. Viewed along the usual axes, I wanted every point farther along the curve to be at least as far right and as high as the previous one. How much wave can fit before part of it turns back?

## Add a slope

For $y=mx+A\sin(kx)$, the derivative is $m+Ak\cos(kx)$. The minimum derivative is $m-|Ak|$, so the graph is nondecreasing exactly when $m\ge |Ak|$. At equality there are isolated horizontal tangents.

## Rotate the curve

Write the original sine wave as $(t,A\sin(kt))$ and rotate it counterclockwise through $0<\theta<90^\circ$:

$$
\begin{aligned}
x(t)&=t\cos\theta-A\sin(kt)\sin\theta,\\
y(t)&=t\sin\theta+A\sin(kt)\cos\theta.
\end{aligned}
$$

The minimum derivatives over a full period are $\cos\theta-|Ak|\sin\theta$ and $\sin\theta-|Ak|\cos\theta$. Both are nonnegative exactly when

$$
|Ak|\le\min(\tan\theta,\cot\theta).
$$

At $45^\circ$, this bound reaches its maximum, $1$. The cover uses $A=k=1$, which gives the curve

$$
x(t)=\frac{t-\sin t}{\sqrt2},\qquad
y(t)=\frac{t+\sin t}{\sqrt2}.
$$

Both coordinates are strictly increasing. At even multiples of $\pi$ the tangent is vertical, and at odd multiples it is horizontal. Increasing the amplitude above one creates sections that go down and other sections that turn left.

The overall slope approaches $1$ as $t\to\pm\infty$. The vertical offset from the diagonal is $y-x=\sqrt2\sin t$, so that offset keeps oscillating.

## How far does it turn back?

At $45^\circ$, set $k=1$ and increase the amplitude to $1+\varepsilon$. The horizontal coordinate decreases near the origin, between $t=-\delta$ and $t=\delta$, where $\delta=\arccos(1/(1+\varepsilon))$. This follows by setting $x'(t)=(1-(1+\varepsilon)\cos t)/\sqrt2$ to zero.

The horizontal distance traveled backward is

$$
x(-\delta)-x(\delta)
=\sqrt2\big((1+\varepsilon)\sin\delta-\delta\big)
=\sqrt2(\tan\delta-\delta)
\sim \frac43\varepsilon^{3/2}.
$$

Here I used $\delta\sim\sqrt{2\varepsilon}$ and $\tan\delta-\delta\sim\delta^3/3$. So the interval in the parameter shrinks like $\sqrt{\varepsilon}$, while the horizontal backtrack shrinks like $\varepsilon^{3/2}$. How much of this survives if I replace sine with another periodic wave?

## Related reading

- The horizontal coordinate at the threshold is proportional to $t-\sin t$, the limiting form of the elliptic Kepler equation as eccentricity tends to one. Inverting the equation near that limit is the subject of [*An improved cubic approximation for Kepler’s equation*](https://academic.oup.com/mnras/article/525/1/57/7220029).
- The same sine perturbation appears in the sine circle map. Jensen, Bak, and Bohr studied [its dynamics at the critical value $K=1$](https://www.nbi.dk/~mhjensen/papers/arnoldton.pdf).
