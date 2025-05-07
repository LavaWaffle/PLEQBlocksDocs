# PL EQ Blocks Attributes

## Overview

The following attributes are available for the PL EQ Blocks element.

### `answers-name`

This parameter is required. It must be unique for each element within a PL question. (This is how data is stored in the database.)

### `solution`

This parameter is required. It is the mathematical expression that sympy will compare the student's answer to. (Please do lots of testing to ensure that this solution is correct, or student's may have trouble using this element.) Any letters used here must also be used in the 'variables' parameter.

### `variables`

This parameter is required. It is a comma separated list of the variables (any letters, not just variables) that will be used in the equation. Note these variables correspond to the variables used in the 'solution' parameter and in the 'eval-as' parameter within the individual answer blocks. The variables are case sensitive and must match in both places.

### `source-blocks-order`

This parameter is optional. It is assumed to be 'random' by default. 

If set to 'random', the blocks will be displayed in a random order.
If set to 'ordered', the blocks will be displayed in the order they are listed in the 'answers' parameter.

### `display-solution`

This parameter is required. This is the latex solution that will be displayed to the student when they correctly answer the question. This answer doesn't have to correspond to the solution parameter. Ot can use completely different variables and or symbols. This is encouraged as sympy prefers simple variables like A, B and so on while mathematical expressions use greek notation.

We make it required because students need to be able to see one expected answer to the question. Thus, they know how the answer should be formatted idealy. Their answer can come in any format, so ideally we'd like to ensure that after answering the question, the student can see the answer as will be used in class.

### Children:

Every child must be a `<pl-answer>` element. They need to have the following attributes:

#### eval-as

This attribute is required. As stated above, this is a variable that will compare the student's answer to the solution. Any letters used here must also be used in the 'variables' parameter.

#### inner html
This attribute is optional (but recommended). This is the latex front end that will be displayed to the student when they answer the question. Again note how the front end and back end don't have to match. This is encouraged. Use mathematical latex notation on the front end and simple letters on the back end.