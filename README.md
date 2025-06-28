# COMPILER-DESIGN-BASICS
COMPANY NAME: CODETECH IT SOLUTION

NAME: ABHILASHA SHARMA

INTERN ID: CT04DF338

DOMAIN: C++

MENTOR: NEELA SANTOSH

#DISCRIPTION:
The provided C++ program is a **mini arithmetic expression compiler** that evaluates mathematical expressions involving basic operators such as addition, subtraction, multiplication, and division. The program supports the use of parentheses to enforce operator precedence and is capable of parsing and evaluating nested expressions. It uses a recursive descent parsing approach, a common method for interpreting expressions based on a grammar, and is implemented in an object-oriented manner using a `Parser` class.

This essay explores the structure, components, and functionality of the program, demonstrating how it breaks down complex expressions into manageable parts for evaluation.

---

### **Program Overview**

At a high level, the program prompts the user to enter a mathematical expression in string form. It then parses and evaluates this expression, displaying the result. The key part of the program lies in the `Parser` class, which encapsulates the logic for interpreting and computing the result of the given expression.

---

### **The `Parser` Class**

The `Parser` class is central to this program. It contains both private data members and methods that work together to analyze and evaluate arithmetic expressions.

#### **Data Members**

* `input`: A string that stores the arithmetic expression to be evaluated.
* `pos`: An integer index that keeps track of the current character position in the input string.

#### **Helper Functions**

1. **`peek()`**: This function returns the current character at the parsing position without advancing the position. If the end of the string is reached, it returns the null character `'\0'`.

2. **`get()`**: This function returns the current character and then increments the position index, effectively consuming the character.

3. **`skipWhitespace()`**: This function skips over any whitespace characters (like spaces or tabs) to ensure that they do not interfere with parsing. It uses the `isspace()` function to identify whitespace.

---

### **Parsing Methods**

The parser uses three levels of recursive functions to handle operator precedence and associativity. These functions reflect the structure of mathematical grammar.

#### 1. **`parseFactor()`**

This is the most basic unit in an expression. It handles numbers and sub-expressions enclosed in parentheses. If it encounters a '(', it recursively calls `parseExpression()` to evaluate the contents inside the parentheses. Otherwise, it parses a number character by character (including decimal points) and converts it to a `double` using `stod()`.

#### 2. **`parseTerm()`**

This function handles multiplication and division. It starts by parsing a factor and then checks whether the next operator is `*` or `/`. If so, it consumes the operator, parses the next factor, and performs the appropriate operation. This ensures that multiplication and division are evaluated before addition and subtraction.

#### 3. **`parseExpression()`**

This is the top-level function that handles addition and subtraction. It begins by parsing a term (which may include products or quotients) and then checks for `+` or `-` operators. It repeatedly applies these operations to terms as long as they continue in the expression.

These three methods ensure that the expression is parsed in a manner consistent with standard mathematical rules of precedence and associativity.

---

### **Public Method: `evaluate()`**

This function is the interface between the parser and the outside world. It initializes the parser by setting the input expression and resetting the position index. It then calls `parseExpression()` to compute the result and returns it.

---

### **The `main()` Function**

The `main()` function handles user interaction. It begins by creating a `Parser` object and prompting the user to input an arithmetic expression. The input is read using `getline()` to allow for spaces in the expression.

The expression is passed to the `evaluate()` function, and the result is printed. If an error occurs during parsing (such as a missing parenthesis or invalid number), a `runtime_error` exception is thrown, which is caught in a `try-catch` block. An appropriate error message is then displayed.

---

### **Conclusion**

This program is a simple but powerful demonstration of how to build a **recursive descent parser** for arithmetic expressions in C++. It handles fundamental concepts of parsing, such as grammar rules, operator precedence, and parentheses, all while maintaining clean and readable code through object-oriented design. Although basic in its scope, this program can serve as the foundation for more complex expression evaluators or interpreters, and introduces key techniques used in building compilers and interpreters in the field of computer science.

OUTPUT:
![Image](https://github.com/user-attachments/assets/0fa95265-de6f-413b-8067-fa7971d7563b)
