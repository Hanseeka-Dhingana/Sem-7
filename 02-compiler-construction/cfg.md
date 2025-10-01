https://www.youtube.com/watch?v=UE0B2io8K5o

1. any number of a's CFG: G = {(S), (a), P, S} # Variables, terminals, Production rule, start symbol

Production Rule:   S -> aS | ɛ


2. Any number of a's and b's

S -> aS | bS | ɛ


3. At least 2 a's

RE = (a+b)* a (a+b)* a (a+b)*

S -> AaAaA
A -> aA | bA | ɛ


4. One Occurrence of 000

S -> A000A
A -> 0A | 1A | ɛ
