# Monitoring and debugging

A simulation is used to obtain an image/idea of real scenarios, so the outcomes can be used in the 'real world'. It's effectively a *model*. 

It is often hard to know whether a simulation performed correctly simply by looking at the outcome. In the case of the apple before, you can analytically calculate the outcome. But this quickly becomes cumbersome. In addition, for many applications analytical solutions do not even exist.

That's why it is so important to systematically check a simulation. Here are a few pointers that should aid in doing so:

1. Check using pen and paper whether the core of your calculation is correct: are you working towards the right direction? If it becomes too complicated it's sometimes better to make a rough estimation and compare that to your simulation.

2. Have you looked up the correct constants and formulas? Verify them another time. Are the constants precise enough? A rounding error can increase incredibly quick!

3. Are your time steps sufficiently small? If the outcome becomes very different by adapting the time step size, your time step is probably not small enough yet!

4. Are the components of the simulation in the correct order? Make sure each step calculates all values in the correct order. Only when that is done check the values themselves and if those are correct.

Finally a tip for debugging a simulation. You can print all values at each time step. This way, you can precisely inspect them and see if an error occurred at some point. Or if maybe the starting values were already incorrect!
