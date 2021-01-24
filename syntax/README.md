# Here is an example of Heron in Brackus Naur Form

*keep in mind that I am very new to writing BNF grammar*
> If you would like the *raw* BNF, click [here](heron.bnf)
> If you would like an *interactive* look at the Heron BNF, click [here](https://bnfplayground.pauliankline.com/?bnf=%3CEOS%3E%20%3A%3A%3D%20%22%3B%22%0A%0A%3Cdigit%3E%20%3A%3A%3D%20%5B0-9%5D%20%7C%20%22.%22%0A%3Cletter%3E%20%3A%3A%3D%20%22A%22%20%7C%20%22B%22%20%7C%20%22C%22%20%7C%20%22D%22%20%7C%20%22E%22%20%7C%20%22F%22%20%7C%20%22G%22%20%7C%20%22H%22%20%7C%20%22I%22%20%7C%20%22J%22%20%7C%20%22K%22%20%7C%20%22L%22%20%7C%20%22M%22%20%7C%20%22N%22%20%7C%20%22O%22%20%7C%20%22P%22%20%7C%20%22Q%22%20%7C%20%22R%22%20%7C%20%22S%22%20%7C%20%22T%22%20%7C%20%22U%22%20%7C%20%22V%22%20%7C%20%22W%22%20%7C%20%22X%22%20%7C%20%22Y%22%20%7C%20%22Z%22%20%7C%20%22a%22%20%7C%20%22b%22%20%7C%20%22c%22%20%7C%20%22d%22%20%7C%20%22e%22%20%7C%20%22f%22%20%7C%20%22g%22%20%7C%20%22h%22%20%7C%20%22i%22%20%7C%20%22j%22%20%7C%20%22k%22%20%7C%20%22l%22%20%7C%20%22m%22%20%7C%20%22n%22%20%7C%20%22o%22%20%7C%20%22p%22%20%7C%20%22q%22%20%7C%20%22r%22%20%7C%20%22s%22%20%7C%20%22t%22%20%7C%20%22u%22%20%7C%20%22v%22%20%7C%20%22w%22%20%7C%20%22x%22%20%7C%20%22y%22%20%7C%20%22z%22%0A%0A%3CidentifierCharacter%3E%20%3A%3A%3D%20%3Cletter%3E%20%7C%20%3Cdigit%3E%20%7C%20%22.%22%20%7C%20%22%3E%22%20%7C%20%22%2B%22%20%7C%20%22%23%22%20%7C%20%22%3A%22%20%7C%20%22!%22%20%7C%20%22%25%22%20%7C%20%22*%22%20%7C%20%22(%22%20%7C%20%22)%22%20%7C%20%22-%22%20%7C%20%22%2B%22%0A%3Cidentifier%3E%20%3A%3A%3D%20%3CidentifierCharacter%3E%20%7C%20%3Cidentifier%3E%20%3CidentifierCharacter%3E%0A%0A%3Ccharacter%3E%20%3A%3A%3D%20%3CidentifierCharacter%3E%20%7C%20%22%40%22%20%7C%20%22%24%22%20%7C%20%22%5E%22%20%7C%20%22%26%22%20%7C%20%22%3D%22%20%7C%20%22%7B%22%20%7C%20%22%7D%22%20%7C%20%22%3F%22%20%7C%20%22%3E%22%20%7C%20%22%3C%22%20%7C%20%22%2C%22%20%7C%20%22%60%22%20%7C%20%22~%22%20%7C%20%22%5B%22%20%7C%20%22%5D%22%20%7C%20%22%3B%22%20%7C%20%22%20%22%20%7C%20%22%5Cn%22%0A%3Cany%3E%20%3A%3A%3D%20%3Ccharacter%3E%20%7C%20%3Cany%3E%20%3Ccharacter%3E%0A%0A%3Cquote%3E%20%3A%3A%3D%20%22%27%22%20%7C%20%22%5C%22%22%0A%3Cstring%3E%20%3A%3A%3D%20%20%3Cquote%3E%20%3Cany%3E%20%3Cquote%3E%0A%0A%3Cimport%3E%20%3A%3A%3D%20%22%40import%22%20%3Cstring%3E%20%3CEOS%3E%0A%0A%3Cproperty%3E%20%3A%3A%3D%20%3Cidentifier%3E%20%22%3A%22%20%3Cidentifier%3E%20%3CEOS%3E%0A%3Ccontent%3E%20%3A%3A%3D%20(%3Cproperty%3E%20%7C%20%3CstyleRule%3E)%20%7C%20%3Ccontent%3E%20(%3Cproperty%3E%20%7C%20%3Crule%3E)%0A%0A%3CstyleRule%3E%20%3A%3A%3D%20%3Cidentifier%3E%20%22%7B%22%20%3Ccontent%3E%20%7C%20%3CstyleRule%3E%20%22%7D%22%0A%0A%3Crule%3E%20%3A%3A%3D%20%3Cimport%3E%20%7C%20%3CstyleRule%3E%0A%3Cstylesheet%3E%20%3A%3A%3D%20%3Crule%3E%20%7C%20%3Cstylesheet%3E%20%3Crule%3E&name=)

# Primitive Type Literals

## End-of-Statement Token

```
<EOS> ::= ";"
```

## Digit

```
<digit> ::= [0-9] | "."
```

## Letters

```
<letter> ::= "A" | "B" | "C" | "D" | "E" | "F" | "G" | "H" | "I" | "J" | "K" | "L" | "M" | "N" | "O" | "P" | "Q" | "R" | "S" | "T" | "U" | "V" | "W" | "X" | "Y" | "Z" | "a" | "b" | "c" | "d" | "e" | "f" | "g" | "h" | "i" | "j" | "k" | "l" | "m" | "n" | "o" | "p" | "q" | "r" | "s" | "t" | "u" | "v" | "w" | "x" | "y" | "z"
```

## Identifier Character

```
<identifierCharacter> ::= <letter> | <digit> | "." | ">" | "+" | "#" | ":" | "!" | "%" | "*" | "(" | ")" | "-" | "+"
<identifier> ::= <identifierCharacter> | <identifier> <identifierCharacter>
```

this represent any character that belongs to an identifier

## Character

```
<character> ::= <identifierCharacter> | "@" | "$" | "^" | "&" | "=" | "{" | "}" | "?" | ">" | "<" | "," | "`" | "~" | "[" | "]" | ";" | " " | "\n"
<any> ::= <character> | <any> <character>
```

## Strings

```
<quote> ::= "'" | "\""
<string> ::=  <quote> <any> <quote>
```

# At-rules

## Import

```
<import> ::= "@import" <string> <EOS>
```

# Rules

## Property

```
<property> ::= <identifier> ":" <identifier> <EOS>
<content> ::= (<property> | <styleRule>) | <content> (<property> | <rule>)
```

## A Style Rule

```
<styleRule> ::= <identifier> "{" <content> | <styleRule> "}"
```

## Rule

```
<rule> ::= <import> | <styleRule>
```

## Stylesheet

```
<stylesheet> ::= <rule> | <stylesheet> <rule>
```
