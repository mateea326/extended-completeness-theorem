# Extended Completeness Theorem

A formal study of proof theory in Propositional Logic, extending the classical Completeness Theorem to countably infinite sequents ($\Gamma \to \Delta$, where $\Gamma$ and $\Delta$ may contain infinitely many formulas). 

## The Core Concept
The classical theorem proves that valid finite sequents have formal proofs. This project demonstrates that even for infinite sequents, a sequent is valid if and only if it is provable.

## The Proof Mechanism

The proof relies on systematically decomposing formulas using the **Gentzen System G** and a deterministic **Search Procedure**. Because the input lists are infinite, the procedure uses queues (Queue L and Queue R) to ensure no formula is ignored. 

Given any sequent, the Search Procedure builds a proof tree from the root upwards, guaranteeing one of two outcomes:

### Case 1: The Sequent is Valid
If the sequent is valid, counterexamples are impossible. The Search Procedure is forced to terminate. Every branch of the tree closes by reaching an Axiom (the same atom appearing on both the left and right sides). This results in a finite formal proof, demonstrating the Compactness Theorem (only a finite subset of the infinite premises is needed to prove the conclusion).

### Case 2: The Sequent is Invalid (Falsifiable)
If the sequent is invalid, the tree will not close. The procedure handles this through a strict mathematical pipeline:
1. **König's Lemma:** Because the tree does not close and the rules create at most 2 children per node, König's Lemma guarantees the existence of at least one infinite path.
2. **Hintikka Sets:** Since this infinite path never hits an axiom, its formulas never contradict each other. This contradiction-free path naturally forms a Hintikka set.
3. **Falsifying Valuation:** Using the Extraction and Satisfiability Lemmas, we can extract an explicit valuation from this Hintikka set. This provides the counterexample.

## Main Theorems

* **Theorem 3.5.1:** The Search Procedure perfectly categorizes any sequent—it either produces a closed proof tree or constructs a falsifying valuation.
* **Theorem 3.5.2 (Extended Completeness & Soundness):** 
  * *Completeness:* If a sequent is valid, no falsifying valuation exists, meaning the Search Procedure will always produce a proof.
  * *Soundness:* If the procedure outputs a formal proof, the root sequent is guaranteed to be valid.

## Conclusion
Every valid possibly infinite sequent is guaranteed to have a finite formal proof.