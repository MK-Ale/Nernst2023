# Ions in Neurons

This lab was created by Marianne Bezaire, PhD

The electrical behavior of neurons depends on the intracellular and extracellular ions, especially on ions capable of crossing the neuron's membrane. At rest, the neuron's membrane potential is mostly determined by the ions potassium (K+), sodium (Na+) and chloride (Cl-) as well as negatively charged proteins inside the neuron.

<img title="Membrane permeable ions" src="https://github.com/mbezaire/labs/blob/rise/nernst/ions.png?raw=true" width=400>

<br>

These three ions are unevenly concentrated across the cell membrane. Inside the cell, K+ is much more abundant than outside. Conversely, Na+ and Cl- are much more prevelant in the extracellular space. The ions cannot freely cross the membrane; they can only cross when ion channels in the membrane open. And they can only pass through specific types of ion channels - not all channels allow all types of ions through.

In addition to these concentration gradients across the membrane, there is also a difference in charge, leading to a membrane potential of around -70 mV. This means the inside of the neuron is negatively charged relative to the extracellular space outside of the neuron.

<br>

## Reversal Potential 

The charge difference across the membrane and the concentration gradients impel the ions to cross the membrane when they can (ie, when ion channels in the membrane open, allowing specific types of ions to cross). 

The direction in which the ions cross depends on the concentration gradient and the electrical charge difference. Sometimes these forces are in opposition. For example, potassium is more highly concentrated in the cell and therefore should exit the cell when channels are open. However, inside the cell is much more negatively charged, which is attractive to the positively charged potassium ion.

<br>

<img title="Ions at the Membrane" src="https://github.com/mbezaire/labs/blob/rise/nernst/membrane.png?raw=true" width=400>

To determine which direction a particular ionic current will flow when its channels are open, we can calculate a property called the reversal potential of the ion. The reversal potential is the membrane potential at which the current will switch directions (ions flowing in versus out of the cell).

<br>

## Nernst Equation

We can calculate the reversal potential of an ion using the Nernst Equation.

<img src="https://latex.codecogs.com/svg.image?E_R&space;=&space;\frac{RT}{zF}ln\frac{[X]_{out}}{[X]_{in}}">

where [X] refers to the concentration of ion X either inside or outside the neuron and z refers to the valence of ion X (+1 for potassium or sodium, -1 for chloride).

<br>
*R is the gas constant, 8.314 J/(K * mol)
*T is the temperature in Kelvins (K)
*F is Faraday's constant, 96485.3 Coulombs (C) / mol
<br>

Let's create a Python function that can calculate the reversal potential of an ion, given its intracellular and extracellular concentrations and its valence.

<br>

## Building the function

Open nernst.py to begin. 

**Note:** you may work in a file called nernst.py within https://code.cs50.io or on your own IDE.

First, we'll define a function called `nernst` that takes in three arguments:
* the valence of the ion
* the intracellular concentration of the ion in mM
* the extracellular concentration of the ion in mM

This function should return a variable calculated inside the function.

<br>
<br>

<details>
<summary>Spoiler "See Code"</summary>
<pre>
def nernst(valence, conc_in, conc_out):
    rev_pot = 0
    <br>
    return rev_pot
</pre>
</details>

<br>
<br>

Now, let's add the body of the `nernst` function. In the function, write code to calculate the reversal potential of an ion using the Nernst equation and the information passed as arguments to the function.

Checking our units, it seems that our reversal potential will be calculated in units of volts (V). However, units of milliVolts would be more useful for us. To convert, multiply the right side of the Nernst equation by a factor of 1000.

Note: we can use the `math` library in Python to calculate the natural log, `ln`. The command we will use is `math.log()`; by default, the `log` method of math uses `e` as its base.

<br>
<br>

<details>
<summary>Spoiler "See Code"</summary>
<pre>
def nernst(valence, conc_in, conc_out)
    rev_pot = # plug in the nernst equation here<br>
    return rev_pot   
</pre>
</details>

<br>
<br>

Now, let's add code that calls our function. We will need to place this section of code below our `nernst` function. We will need to un-indent the code as well, so that it is not part of our `nernst` function.

Let's call the function using data that represents potassium: a valence of 1, an intracellular concentration of approximately 140 mM, and an extracellular concentration of 3 mM.

Since the function should return a value, let's assign the output of the function (the function call will evaluate to this output) to a new variable. Next, print the new variable so we can see what our function calculates for the reversal potential.

<br>
<br>

<details>
<summary>Spoiler "See Hint"</summary>
To call a function in python, type the name of the function with open and close parenthesis (). Some functions, like our `nernst` function, expect to receive arguments in the parenthesis. We must put all three of our arguments in the function, in the same order as our function definition, and separate them with commas.
</details>

<br>
<br>

Now let's run the code and test it. To execute the code file, enter in the terminal window: `python nernst.py`.

Verify that the code prints something like -85.565 when ran with the parameters given above (1, 140, 5).

<br>

## Check the Code

After confirming that the equation is calculating correctly, let's update our code so that it takes user input for the ion information rather than hard-coding the numbers into our program.

Use `input` function calls with appropriate prompts to set the values for the valence, and the internal and external concentration arguments that are passed to the `nernst` function.

Make sure to convert the values assigned from the `input()` call to integers before passing them to the `nernst` function.

<br>
<br>

<details>
<summary>Spoiler "See Hint"</summary>
<pre>
my_integer = int(input("Enter an integer: ")) 
</pre>
</details>

<br>
<br>

You can now test your code against our auto-checker by executing the command below in the terminal:

```
check50 --local mbezaire/checks/main/rise/nernst
```

Once you are satisfied with your work, you can submit it. First, follow the steps to get a [Github Personal Access Token](https://cs50.readthedocs.io/github/#personal-access-token) if you haven't yet. Then execute this command in the terminal to submit:

```
submit50 mbezaire/checks/main/rise/nernst
```
