# Welcome to the PL EQ Blocks Docs

## Overview

PrairieLearn Equation Blocks is a custom element for [PrairieLearn](https://github.com/PrairieLearn/PrairieLearn) that allows you to test users on mathematical equations.

The project is a mix between [pl-order-blocks](https://prairielearn.readthedocs.io/en/latest/elements/#pl-order-blocks-element) and [pl-symbolic-input](https://prairielearn.readthedocs.io/en/latest/elements/#pl-symbolic-input-element). It takes the drag and drop, set in stone input approach of pl-order-blocks and combines it with the complex sympy evaluation of pl-symbolic-input. This allows for the best of both worlds! It gives students a starting point with a set of blocks to build equations with. Then, it enables students to give a variety of valid answers thanks to the power of sympy.

![type:video](./videos/showcase.mp4)

## How to install
Copy the element code into your prairielearn elements directory. The code can be found [here](https://github.com/PrairieLearn/pl-uiuc-mse458/tree/master/elements/pl-eq-blocks).


## Example usage
Within your PrairieLearn Question, add the following code:
```html
<pl-eq-blocks
  answers-name="pyth-formula"
  solution="A^2 + B^2 = C^2"
  variables="A, B, C"
  source-blocks-order="random"
  display-solution="$A^2 + B^2 = C^2$"
>
  <pl-answer eval-as="A^2">$A^2$</pl-answer>
  <pl-answer eval-as="+">$+$</pl-answer>
  <pl-answer eval-as="-">$-$</pl-answer>
  <pl-answer eval-as="B^2">$B^2$</pl-answer>
  <pl-answer eval-as="C^2">$C^2$</pl-answer>
  <pl-answer eval-as="=">$=$</pl-answer>
</pl-eq-blocks>
```
