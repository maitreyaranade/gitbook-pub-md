-   Constant is something that never changes. In other words, once
    defined cannot be modified later in the code.

-   #define is a preprocessor directive.

    -   Syntax: #define name value (name is also called macro)

    -   Avoid semicolon at the end in the syntax.

    -   Choosing capital letters for name is good practice.

    -   Preprocessor replaces Name with value.

    -   We can use macros like functions.

    -   First expansion then evaluation.

    -   There are current predefined / standard Macros ex. \_\_TIME\_\_
        & \_\_DATE\_\_.

-   Const keyword

    -   A variable defined with the const modifier are considered
        variables, and not macro definitions.

    -   syntax: const data_type variable_name

-   Const-s are handled by the compiler, where as #define-s are handled
    by the pre-processor.

-   The big advantage of const-s over #define is type checking.
    #define-s can't be type checked.

-   Since const-s are considered variables, we can use pointers on them.
    This means we can typecast, move addresses, and everything else
    you'd be able to do with a regular variable besides change the data
    itself, since the data assigned to that variable is constant.
