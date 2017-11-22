# First-Order-Logic-Inference-Engine
This implements a FOL Inference engine using backward chaining and resolution on a KB of statements in CNF Form.

The knowledge bases which you will create to handle each case will contain sentences with the following defined operators:
NOT X is represented as ~X
X OR Y is represented as X | Y

# Format for input.txt:
<NQ = NUMBER OF QUERIES>
<QUERY 1>
…
<QUERY NQ>
<NS = NUMBER OF GIVEN SENTENCES IN THE KNOWLEDGE BASE>
<SENTENCE 1>
…
<SENTENCE NS>

where
• Each query will be a single literal of the form Predicate(Constant) or ~Predicate(Constant).
• Variables are all single lowercase letters.
• All predicates (such as Sibling) and constants (such as John) are case-sensitive alphabetical strings that
begin with an uppercase letter.
• Each predicate takes at least one argument. Predicates will take at most 100 arguments. A given
predicate name will not appear with different number of arguments.
• There will be at most 100 queries and 1000 sentences in the knowledge base.
• See the sample input below for spacing patterns.

# Format for output.txt:
For each query, determine if that query can be inferred from the knowledge base or not, one query per line:
<ANSWER 1>
…
<ANSWER NQ>
where
each answer would either be TRUE if we can prove that the corresponding query sentence is true given the
knowledge base, or FALSE if we cannot.
  
Loops in the KB inference has been handled with terminating after a certain number of iterations. This was done to restrict inferring same Knowledge again and again. In such case, the query evaluates to a FALSE.

# Example of Input--

2
Ancestor(Liz,Billy)
Ancestor(Liz,Joe)
6
Mother(Liz,Charley)
Father(Charley,Billy)
~Mother(x,y) | Parent(x,y)
~Father(x,y) | Parent(x,y)
~Parent(x,y) | Ancestor(x,y)
~Parent(x,y) | ~Ancestor(y,z) | Ancestor(x,z)

# Example of Output--

TRUE
FALSE
