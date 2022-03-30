# A Definition of Classes
## [Syntax 1] Variables
### Hypotheses
$ \mathrm{var} \ x $
### Assertion
$ \mathrm{term} \ x $
### Remarks
1. $ \mathrm{var} \ x $ is a statement that means "$ x $ is a variable."
1. $ \mathrm{term} \ x $ is a statement that means "$ x $ is a term."
1. This syntax means that a variable denotes a term.

## [Syntax 2] Sets
### Hypotheses
$ \mathrm{term} \ a $
### Assertion
$ \mathrm{wff} \ \mathrm{set} \ a $
### Remarks
1. $ \mathrm{wff} \ \varphi $ is a statement that means "$ \varphi $ is a wff (well-formed formula)."
1. This syntax means that if $ a $ is a term, then $ \mathrm{set} \ a $ is a wff.
1. $ \mathrm{set} \ a $ is a wff that means "$ a $ is a set."

## [Syntax 3] Classes
### Hypotheses
$ \mathrm{term} \ A $
### Assertion
$ \mathrm{wff} \ \mathrm{class} \ A $
### Remarks
1. This syntax means that if $ A $ is a term, then $ \mathrm{class} \ A $ is a wff.
1. $ \mathrm{class} \ A $ is a wff that means "$ A $ is a class."

## [Syntax 4.1] Class Abstraction (1)
### Hypotheses
1. $ \mathrm{wff} \ \varphi $
1. $ \mathrm{var} \ x $
### Assertion
$ \mathrm{term} \ \left \{ x \ \middle| \ \varphi \right \} $
### Remarks
This syntax means that a class abstraction is a term.

## [Definition 4.2] Class Abstraction (2)
### Hypotheses
1. $ \mathrm{wff} \ \varphi $
1. $ \mathrm{var} \ x $
### Assertion
$ \mathrm{class} \ \left \{ x \ \middle| \ \varphi \right \} $
### Remarks
This definition means that a class abstraction is a class.

## [Definition 4.3] Class Abstraction (3)
### Hypotheses
1. $ \mathrm{wff} \ \varphi $
1. $ \mathrm{var} \ x \ y $
### Assertion
$ \forall x \left [ \mathrm{class} \ x \rightarrow \left ( x \in \left \{ y \ \middle| \ \varphi \right \} \leftrightarrow \mathrm{set} \ x \wedge \left [x / y \right] \varphi \right ) \right ] $
### Remarks
1. $ \mathrm{var} \ x \ y $ is a statement that means "$ x $ and $ y $ are variables."
1. $ \left [x / y \right] \varphi $ is the wff that results from the proper substitution of $ y $ for $ x $ in the wff $ \varphi $. That is, $ y $ properly replaces $ x $. (Megill 1993)

## [Syntax 5.1] The Russell Class (1)
### Assertion
$ \mathrm{term} \ \mathrm{Ru} $
### Remarks
This syntax means that the Russell class is a term.

## [Definition 5.2] The Russell Class (2)
### Hypotheses
$ \mathrm{var} \ y $
### Assertion
$ \mathrm{Ru} = \left \{ y \ \middle| \ y \notin y \right \} $
### Remarks
The Russell class is the class of all sets that are not members of themselves.

## [Lemma 5.3] The Russell Class (3)
### Assertion
$ \mathrm{class} \ \mathrm{Ru} $
### Proof
1. $ \mathrm{var} \ y $ (Metavariable-type hypothesis)
1. $ \mathrm{wff} \ y \notin y $ (1, The syntax of axiomatic set theory)
1. $ \mathrm{class} \ \left \{ y \ \middle| \ y \notin y \right \} $ (2, 1, Definition 4.2)
1. $ \mathrm{Ru} = \left \{ y \ \middle| \ y \notin y \right \} $ (1, Definition 5.2)
1. $ \mathrm{class} \ \mathrm{Ru} $ (4, 3, $ = $-rewriting)
### Remarks
The Russell class is a class.

## [Theorem 6] Russell's Paradox
### Assertion
$ \mathrm{Ru} \notin \mathrm{Ru} \wedge \neg \mathrm{set} \ \mathrm{Ru} $
### Proof
1. $ \mathrm{var} \ x \ y $ (Metavariable-type hypothesis)
1. $ \mathrm{wff} \ y \notin y $ (1, The syntax of axiomatic set theory)
1. $ \forall x \left [ \mathrm{class} \ x \rightarrow \left ( x \in \left \{ y \ \middle| \ y \notin y \right \} \leftrightarrow \mathrm{set} \ x \wedge \left [x / y \right] y \notin y \right ) \right ] $ (2, 1, Definition 4.3)
1. $ \forall x \left [\mathrm{class} \ x \rightarrow \left ( x \in \left \{ y \ \middle| \ y \notin y \right \} \leftrightarrow \mathrm{set} \ x \wedge x \notin x \right ) \right] $ (3, Proper substitution)
1. $ \mathrm{term} \ \mathrm{Ru} $ (Syntax 5.1)
1. $ \mathrm{class} \ \mathrm{Ru} \rightarrow \left ( \mathrm{Ru} \in \left \{ y \ \middle| \ y \notin y \right \} \leftrightarrow \mathrm{set} \ \mathrm{Ru} \wedge \mathrm{Ru} \notin \mathrm{Ru} \right ) $ (5, 4, $ \forall $-elimination)
1. $ \mathrm{Ru} = \left \{ y \ \middle| \ y \notin y \right \} $ (1, Definition 5.2)
1. $ \mathrm{class} \ \mathrm{Ru} \rightarrow \left ( \mathrm{Ru} \in \mathrm{Ru} \leftrightarrow \mathrm{set} \ \mathrm{Ru} \wedge \mathrm{Ru} \notin \mathrm{Ru} \right ) $ (7, 6, $ = $-rewriting)
1. $ \mathrm{class} \ \mathrm{Ru} $ (Lemma 5.3)
1. $ \mathrm{Ru} \in \mathrm{Ru} \leftrightarrow \mathrm{set} \ \mathrm{Ru} \wedge \mathrm{Ru} \notin \mathrm{Ru} $ (9, 8, Modus ponens)
1. $ \mathrm{Ru} \notin \mathrm{Ru} \wedge \neg \mathrm{set} \ \mathrm{Ru} $ (10, Definitions of conjunction and logical equivalence)
### Remarks
1. Let $ \varphi $ and $ \psi $ be wffs. If $ \varphi \leftrightarrow \psi \wedge \neg \varphi $ is true, then $ \neg \varphi \wedge \neg \psi $ is also true. This is a result of the definitions of conjunction and logical equivalence, and is used in Step 11 of the above proof.
1. Since the Russell class is not a set, it is not an element of any classes. Therefore, the Russell class is not an element of itself.
1. A proper class is a class that is not a set. The Russell class is a proper class.
1. All sets are classes. We omit the proof here.
1. Cf. Takeuti and Zaring 1982, chap. 4.

## References
1. Megill, Norman. 1993. “df-sb.” Metamath Proof Explorer. Last modified May 10, 1993. http://us.metamath.org/mpeuni/df-sb.html.
1. Takeuti, Gaisi, and Wilson M. Zaring, *Introduction to Axiomatic Set Theory*, Springer-Verlag, New York, second edition (1982) [QA248.T136 1982].