
#### 1. Regular Languages
- A language is **regular** if it can be described using a **regular expression**.  
- Regular languages are exactly the set of languages that can be recognized by **finite automata (DFA or NFA)**.  
- Regular expressions provide an **algebraic representation** of these languages.  
- Regular languages are **closed** under the following operations:  
  - **Union**  
  - **Concatenation**  
  - **Kleene star** `(*)`  
  - **Intersection and Complement**  



#### 2. Pumping Lemma
The **Pumping Lemma** is a theoretical tool used to **prove that certain languages are not regular**.

- **Pumping:** Repeating a specific substring multiple times.  
- **Lemma:** An intermediate result (theorem) used in proofs.  

There are two versions of the pumping lemma:  
1. For **regular languages**  
2. For **context-free languages**  


#### 3. Pumping Lemma for Regular Languages

##### Theorem
If **\(L\)** is a regular language, then there exists a **pumping length** \(p > 0\) such that every string \(s \in L\) with \(|s| \geq p\) can be split into three parts \(s = xyz\), satisfying:

1. \( xy^i z \in L \quad \forall \; i \geq 0 \)  
2. \( |y| > 0 \)  
3. \( |xy| \leq p \)  



##### Explanation
- In a **finite automaton**, if a string’s length exceeds the number of states (\(p\)), then by the **pigeonhole principle**, at least one state is **visited more than once**.  
- This repetition forms a **loop**, corresponding to the substring \(y\).  
- The loop can be **repeated (pumped)** or removed, generating new strings of the form \( xy^i z \).  
- All such strings must also belong to the language \(L\), if \(L\) is regular.  
- If this property fails for some language, then that language is **not regular**.  



#### 4. Steps to Apply the Pumping Lemma
1. **Assume** the language \(L\) is regular.  
2. Let \(p\) be the **pumping length**.  
3. Choose a string \(s \in L\) with \(|s| \geq p\).  
4. Split \(s = xyz\), where:  
   - \(x\): Prefix (possibly empty)  
   - \(y\): The substring to be pumped (\(|y| > 0\))  
   - \(z\): Suffix (possibly empty)  
   - Constraint: \( |xy| \leq p \)  
5. **Pump \(y\):** Form strings of the type \( xy^i z \), for \(i = 0, 1, 2, \dots\).  
6. **Check membership:** If for some \(i\), \( xy^i z \notin L \), then \(L\) is **not regular**.  
7. Conclude that the assumption is false, hence \(L\) is **non-regular**.  



#### 5. Why the Lemma Holds
- Finite automata have a **limited number of states**.  
- Long strings force **repetition of states**, creating **loops**.  
- These loops can be repeated or skipped without leaving the language.  
- This proves that **all regular languages satisfy the Pumping Lemma**.  
- Therefore, the lemma is a powerful tool to **demonstrate non-regularity**.  
