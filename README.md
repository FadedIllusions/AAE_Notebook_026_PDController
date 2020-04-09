# AAE_Notebook_026_PDController
![P Controller Oscillations](/images/oscillations.png)

Though proportional controllers improve over the quadratic error of open loop controllers, it does have its downfalls -- mainly, the oscillation seen in the above diagram.

No matter how we tune our p-controller, we will always have some degree of oscillatory overshoot. In example, assuming we somehow managed to have z_target and z_actual be one in the same, if there we a sudden and large change in the desired altitude, z_target, of our monorotor, the p-controller would command a rather large thrust_total to compensate. So, how do we remedy this? We need some way to slow or dampen the thrust as z_actual nears z_target.

***   ***   ***   ***   ***   ***   ***   ***   ***

![PD Controller](/images/pd_control.png)

With the Proportional-Derivative (PD) Controller, in addition to setting acceleration in proportion to the error, we also look at the rate of change (derivative) of error. Thus, while the p-term is responsible for adjusting the thrust so that z_target is equal to z_actual (via acceleration), the d-term is responsible for adjust the vehicle's velocity matches the target velocity.

![D Term Error](/images/d_error.png)

***   ***   ***   ***   ***   ***   ***   ***   ***

![PD Code](/images/trust_control.png)

***   ***   ***   ***   ***   ***   ***   ***   ***
