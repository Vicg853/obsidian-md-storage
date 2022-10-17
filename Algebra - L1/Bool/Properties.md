Some properties that are good to keep in mind (not anything required, but will definitely will speed up your thinking process).

#### Simple properties
- $P \land \lnot P$ is always invalid
- $P \lor \lnot P$ is always valid
- $P \iff (P \land P) \iff (P \lor P) \iff \lnot(\lnot P)$

#### Always true assertions
- $(P \land Q) \iff (Q \land P)$
- $(P \lor Q) \iff (Q \lor P)$
- $(P \land (Q \land R)) \iff ((Q \land P) \land R)$
- $(P \lor (Q \lor R)) \iff ((Q \lor P) \lor R)$

#### Always true assertions (more complex)
- The following ones should remind us about distributivity:
	- $(P \land (Q \lor R)) \iff ((P \land Q) \lor (P \land R))$
	- $(P \lor (Q \land R)) \iff ((P \lor Q) \land (P \lor R))$
- $\lnot (P \land Q) \iff (\lnot P \lor \lnot Q)$
- The "implication of transitivity" law: 
  $((P \implies Q) \land (Q \implies R) \implies P \implies R = (R \lor \lnot P) \lor \lnot((Q \lor \lnot P) \land (R \lor \land Q))$
- Contraposition's law: $(P \implies Q) \iff (\lnot Q \implies \lnot P)$
	- And its negation: $\lnot(P \implies Q) \iff P \land \lnot Q$
- The necessary and sufficient condition: $(P \iff Q) \iff ((P \implies Q) \land (Q \implies P)) \iff (Q \lor \lnot P) \land (P \lor \lnot Q)$ 