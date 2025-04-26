In this project I'm creating a C Compiler. But what's interesting about this project is that as we progress we are visualizing each step of our compiler so that it becomes easier for a student to understand the phases of compiler with ease.

As of now I have created a Lexer and Parser and created a UI for interactivity purposes.

Lexer takes the C code as input and breaks the code into a set of tokens.

Token is nothing but a lexeme encapsulated with it's type. We have following types of tokens:
1. Keywords
2. Identifiers
3. Open Parenthesis
4. Closing Parenthesis
5. Opening Brace - Indicating the start of a block statement
6. Closing Brace - Indicating the end of a block statement
7. String Literals
8. Comments
9. Numbers
10. Operators
11. Undefined - For those lexemes which have not yet been defined by us.

Parser has the following role:
I have created a recursive descent parser to generate an AST (Abstract Syntax Tree) when the tokens are given as input by the lexer.

These are some of the nodes that we are creating recursively within our parser:

1.	functionDeclaration Node:
{
	"type":
	"returnType":
	"name":
	"parameters":[]
	"body":[]
}

2.	parameter Node:
{
	"type":
	"paramType":
	"paramName":
}

3.	compoundStatement Node:
{
	"type":
	"body": []
}

4.	returnStatement Node:
{
	"type":
	"expression":
}
 
5.	if/else statement Node:
{
	"type":
	"condition":
	"then":
	"else":
}

6.	for loop statement Node:
{
	"type":
	"initialization":
	"condition":
	"body": {statement or compoundStatement Node}
}

7.	declarationStatement Node:
{
	"type":
	"varType":
	"variables":[]
}

8.	variableDeclarator Node:
{
	"type":
	"name":
	"initializer":{"type":
		           "value":
	              }
}
9.	expressionStatement Node:
{
	"type":
	"expression":{"type":
	              "operator":
		          "left":
		          "right":
		         }
}

10.	postfixExp Node:
{
	"type":
	"operator":
	"argument":{"type":
		        "name":
		       }
}


11.	prefixExp Node:
{
	"type":
	"operator":
	"argument": {"type":
	             "name":
	            }
}



12.	literal Node:
{
	"type":
	"value":
}

13.	functionCall Node:
{
	"type":
	"name":
	"arguments":[]
}

14.	identifier Node:
{
	"type":
	"name":
}

15. program Node
{
  "type":
  "body":[]
}


I have used JavaScript to create the entire implemention part of this project and used HTML + CSS for creating the layout and styling of the page.
