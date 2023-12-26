# What is token?
* What is a token? A lexical token is a sequence of characters that can be treated as a unit in the grammar of the programming languages. Example of tokens:

*Type token (id, number, real, . . . )
* Punctuation tokens (IF, void, return, . . . )
* Alphabetic tokens (keywords)
* Keywords; Examples-for, while, if etc.
* Identifier; Examples-Variable name, function name, etc.
* Operators; Examples '+', '++', '-' etc.
* Separators; Examples ',' ';' etc
# Example of Non-Tokens:

Comments, preprocessor directive, macros, blanks, tabs, newline, etc.
Lexeme: The sequence of characters matched by a pattern to form the corresponding token or a sequence of input characters that comprises a single token is called a lexeme. eg- “float”, “abs_zero_Kelvin”, “=”, “-”, “273”, “;” . 
#  How Lexical Analyzer works-

* Input preprocessing: This stage involves cleaning up the input text and preparing it for lexical analysis. This may include removing comments, whitespace, and other non-essential characters from the input text.
* Tokenization: This is the process of breaking the input text into a sequence of tokens. This is usually done by matching the characters in the input text against a set of patterns or regular expressions that define the different types of tokens.
* Token classification: In this stage, the lexer determines the type of each token. For example, in a programming language, the lexer might classify keywords, identifiers, operators, and punctuation symbols as separate token types.
* Token validation: In this stage, the lexer checks that each token is valid according to the rules of the programming language. For example, it might check that a variable name is a valid identifier, or that an operator has the correct syntax.
* Output generation: In this final stage, the lexer generates the output of the lexical analysis process, which is typically a list of tokens. This list of tokens can then be passed to the next stage of compilation or interpretation.
  # Advantages
* Efficiency: Lexical analysis improves the efficiency of the parsing process because it breaks down the input into smaller, more manageable chunks. This allows the parser to focus on the structure of the code, rather than the individual characters.

* Flexibility: Lexical analysis allows for the use of keywords and reserved words in programming languages. This makes it easier to create new programming languages and to modify existing ones.

* Error Detection: The lexical analyzer can detect errors such as misspelled words, missing semicolons, and undefined variables. This can save a lot of time in the debugging process.

* Code Optimization: Lexical analysis can help optimize code by identifying common patterns and replacing them with more efficient code. This can improve the performance of the program.

# Disadvantages:
Complexity: Lexical analysis can be complex and require a lot of computational power. This can make it difficult to implement in some programming languages.

* Limited Error Detection: While lexical analysis can detect certain types of errors, it cannot detect all errors. For example, it may not be able to detect logic errors or type errors.

* Increased Code Size: The addition of keywords and reserved words can increase the size of the code, making it more difficult to read and understand.

* Reduced Flexibility: The use of keywords and reserved words can also reduce the flexibility of a programming language. It may not be possible to use certain words or phrases in a way that is intuitive to the programmer.





