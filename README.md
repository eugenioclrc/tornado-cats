<div align="center"><img src="Tornado%20Cats.png" style="width: 512px;"></div><br>

# Please read
This is an automatic translation from the [original documentation](https://github.com/eugenioclrc/tornado-cats/blob/main/README-JP.md)

**Tornado Cats** is a book for learning zero-knowledge applications and decentralized mixing through the creation of a simple mixer protocol based on [Tornado Cash](https://github-com.translate.goog/tornadocash/tornado-core?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp) .

> Warning This repository is for educational purposes only and is not intended to facilitate attacks against protocols and money laundering.
> 

---

**table of contents**

1. [Introduction](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB)
2. [How to proceed hands-on](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%83%8F%E3%83%B3%E3%82%BA%E3%82%AA%E3%83%B3%E3%81%AE%E9%80%B2%E3%82%81%E6%96%B9)
3. [Overview of Tornado Cash](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash%E3%81%AE%E6%A6%82%E8%A6%81)
    1. [What is Tornado Cash?](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash%E3%81%A8%E3%81%AF)
    2. [Anonymization mechanism](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E7%A7%98%E5%8C%BF%E5%8C%96%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF)
    3. [Relayer](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%83%AA%E3%83%AC%E3%82%A4%E3%83%A4%E3%83%BC)
    4. [mixing](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%83%9F%E3%82%AD%E3%82%B7%E3%83%B3%E3%82%B0)
    5. [Inappropriate use that results in loss of anonymity](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%8C%BF%E5%90%8D%E6%80%A7%E3%81%8C%E5%A4%B1%E3%82%8F%E3%82%8C%E3%82%8B%E4%B8%8D%E9%81%A9%E5%88%87%E3%81%AA%E5%88%A9%E7%94%A8)
    6. [Tornado Cash Classic and Tornado Cash Nova](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash-classic%E3%81%A8tornado-cash-nova)
4. [An overview of zero-knowledge proofs](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%BC%E3%83%AD%E7%9F%A5%E8%AD%98%E8%A8%BC%E6%98%8E%E3%81%AE%E6%A6%82%E8%A6%81)
    1. [What is a zero-knowledge proof?](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%BC%E3%83%AD%E7%9F%A5%E8%AD%98%E8%A8%BC%E6%98%8E%E3%81%A8%E3%81%AF)
    2. [Three properties that zero-knowledge proofs should satisfy](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%BC%E3%83%AD%E7%9F%A5%E8%AD%98%E8%A8%BC%E6%98%8E%E3%81%8C%E6%BA%80%E3%81%9F%E3%81%99%E3%81%B9%E3%81%8D3%E3%81%A4%E3%81%AE%E6%80%A7%E8%B3%AA)
        1. [Completeness](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%AE%8C%E5%85%A8%E6%80%A7completeness)
        2. [Soundness](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%81%A5%E5%85%A8%E6%80%A7soundness)
        3. [Zero-knowledge Property](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%BC%E3%83%AD%E7%9F%A5%E8%AD%98%E6%80%A7zero-knowledge-property)
        4. [Specific example: Anonymous money transfer](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%85%B7%E4%BD%93%E4%BE%8B-%E5%8C%BF%E5%90%8D%E9%80%81%E9%87%91%E3%81%AE%E5%A0%B4%E5%90%88)
    3. [How can a zero-knowledge proof be constructed?](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%81%A9%E3%81%86%E3%81%97%E3%81%9F%E3%82%89%E3%82%BC%E3%83%AD%E7%9F%A5%E8%AD%98%E8%A8%BC%E6%98%8E%E3%81%8C%E6%A7%8B%E6%88%90%E3%81%A7%E3%81%8D%E3%82%8B%E3%81%8B)
        1. [problem definition](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%95%8F%E9%A1%8C%E3%81%AE%E5%AE%9A%E7%BE%A9)
        2. [bad example](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E9%A7%84%E7%9B%AE%E3%81%AA%E4%BE%8B)
        3. [good example](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E8%89%AF%E3%81%84%E4%BE%8B)
    4. [Non-interactive zero-knowledge proof](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E9%9D%9E%E5%AF%BE%E8%A9%B1%E5%9E%8B%E3%82%BC%E3%83%AD%E7%9F%A5%E8%AD%98%E8%A8%BC%E6%98%8E)
    5. [zk-SNARK](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#zk-snark)
5. [Environment](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E7%92%B0%E5%A2%83%E6%A7%8B%E7%AF%89)
6. [Basics of Zero-Knowledge Proof Circuits](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%BC%E3%83%AD%E7%9F%A5%E8%AD%98%E8%A8%BC%E6%98%8E%E5%9B%9E%E8%B7%AF%E3%81%AE%E5%9F%BA%E7%A4%8E)
    1. [What is a circuit](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%9B%9E%E8%B7%AF%E3%81%A8%E3%81%AF)
    2. [What is Circom](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#circom%E3%81%A8%E3%81%AF)
    3. [Example Circuit: Factorization](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%9B%9E%E8%B7%AF%E3%81%AE%E4%BE%8B-%E5%9B%A0%E6%95%B0%E5%88%86%E8%A7%A3)
    4. [Compiling the circuit](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%9B%9E%E8%B7%AF%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%91%E3%82%A4%E3%83%AB)
    5. [Rank 1 Constraint System (R1CS)](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#rank-1-constraint-system-r1cs)
    6. [Witness calculation](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%A6%E3%82%A3%E3%83%83%E3%83%88%E3%83%8D%E3%82%B9%E3%81%AE%E8%A8%88%E7%AE%97)
    7. [Setting up a zero-knowledge proof](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%BC%E3%83%AD%E7%9F%A5%E8%AD%98%E8%A8%BC%E6%98%8E%E3%81%AE%E3%82%BB%E3%83%83%E3%83%88%E3%82%A2%E3%83%83%E3%83%97)
        1. [Trusted Setup](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#trusted-setup)
        2. [Trusted Setup Ceremony](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#trusted-setup-ceremony)
        3. [Phase 1](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#phase-1)
        4. [Phase 2](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#phase-2)
    8. [Generating Zero-Knowledge Proofs](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%BC%E3%83%AD%E7%9F%A5%E8%AD%98%E8%A8%BC%E6%98%8E%E3%81%AE%E7%94%9F%E6%88%90)
    9. [Validation of zero-knowledge proofs](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%BC%E3%83%AD%E7%9F%A5%E8%AD%98%E8%A8%BC%E6%98%8E%E3%81%AE%E6%A4%9C%E8%A8%BC)
    10. [Exercise: Multiplier with 3 Input Signals](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-3%E5%80%8B%E3%81%AE%E5%85%A5%E5%8A%9B%E3%82%B7%E3%82%B0%E3%83%8A%E3%83%AB%E3%82%92%E6%8C%81%E3%81%A4%E4%B9%97%E7%AE%97%E5%99%A8)
    11. [Exercise: Multiplier with N Input Signals](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-n%E5%80%8B%E3%81%AE%E5%85%A5%E5%8A%9B%E3%82%B7%E3%82%B0%E3%83%8A%E3%83%AB%E3%82%92%E6%8C%81%E3%81%A4%E4%B9%97%E7%AE%97%E5%99%A8)
    12. [Exercise: A circuit that checks if an input signal is true or false](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-%E5%85%A5%E5%8A%9B%E3%82%B7%E3%82%B0%E3%83%8A%E3%83%AB%E3%81%8C%E7%9C%9F%E5%81%BD%E5%80%A4%E3%81%8B%E3%82%92%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%81%99%E3%82%8B%E5%9B%9E%E8%B7%AF)
    13. [Exercise: Logical AND Circuits](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-%E8%AB%96%E7%90%86and%E5%9B%9E%E8%B7%AF)
    14. [Exercise: N-Input Logical AND Circuit (Optional)](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-n%E5%85%A5%E5%8A%9B%E3%81%AE%E8%AB%96%E7%90%86and%E5%9B%9E%E8%B7%AF%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3)
7. [Configuration of Homebrew Mixer Protocol](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E8%87%AA%E4%BD%9C%E3%83%9F%E3%82%AD%E3%82%B5%E3%83%BC%E3%83%97%E3%83%AD%E3%83%88%E3%82%B3%E3%83%AB%E3%81%AE%E6%A7%8B%E6%88%90)
    1. [Basic policy](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%9F%BA%E6%9C%AC%E6%96%B9%E9%87%9D)
    2. [Exercise: Designing a Mixer Protocol](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-%E3%83%9F%E3%82%AD%E3%82%B5%E3%83%BC%E3%83%97%E3%83%AD%E3%83%88%E3%82%B3%E3%83%AB%E3%81%AE%E8%A8%AD%E8%A8%88)
    3. [Overall structure of the protocol](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%83%97%E3%83%AD%E3%83%88%E3%82%B3%E3%83%AB%E3%81%AE%E5%85%A8%E4%BD%93%E6%A7%8B%E6%88%90)
    4. [Contract configuration](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%B3%E3%83%B3%E3%83%88%E3%83%A9%E3%82%AF%E3%83%88%E6%A7%8B%E6%88%90)
    5. [circuit configuration](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%9B%9E%E8%B7%AF%E6%A7%8B%E6%88%90)
8. [deposit and withdrawal design](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%85%A5%E5%87%BA%E9%87%91%E3%81%AE%E8%A8%AD%E8%A8%88)
    1. [Exercise: Designing a Deposit/Withdrawal Operation](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-%E5%85%A5%E5%87%BA%E9%87%91%E6%93%8D%E4%BD%9C%E3%81%AE%E8%A8%AD%E8%A8%88)
    2. [Bad design example](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E9%A7%84%E7%9B%AE%E3%81%AA%E8%A8%AD%E8%A8%88%E4%BE%8B)
    3. [Bad design example 2](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E9%A7%84%E7%9B%AE%E3%81%AA%E8%A8%AD%E8%A8%88%E4%BE%8B2)
    4. [good design example](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E8%89%AF%E3%81%84%E8%A8%AD%E8%A8%88%E4%BE%8B)
    5. [Selection of algorithms and data structures](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%A2%E3%83%AB%E3%82%B4%E3%83%AA%E3%82%BA%E3%83%A0%E3%81%A8%E3%83%87%E3%83%BC%E3%82%BF%E6%A7%8B%E9%80%A0%E3%81%AE%E9%81%B8%E5%AE%9A)
    6. [What is a Pedersen Hash](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#pedersen%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E3%81%A8%E3%81%AF)
    7. [What is the MiMC Merkle Tree?](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#mimc-merkle%E3%83%84%E3%83%AA%E3%83%BC%E3%81%A8%E3%81%AF)
9. [Implementation of withdrawal circuit](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%87%BA%E9%87%91%E5%9B%9E%E8%B7%AF%E3%81%AE%E5%AE%9F%E8%A3%85)
    1. [Exercise: Defining Signals and Creating Components](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-%E3%82%B7%E3%82%B0%E3%83%8A%E3%83%AB%E3%81%AE%E5%AE%9A%E7%BE%A9%E3%81%A8%E3%82%B3%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%8D%E3%83%B3%E3%83%88%E3%81%AE%E4%BD%9C%E6%88%90)
    2. [Exercise: Check Nullifiers](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-%E3%83%8C%E3%83%AA%E3%83%95%E3%82%A1%E3%82%A4%E3%82%A2%E3%81%AE%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF)
    3. [Exercise: Checking the MiMC Merkle Tree](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-mimc-merkle%E3%83%84%E3%83%AA%E3%83%BC%E3%81%AE%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF)
    4. [Exercise: Checking Recipients, Fees, and Relayers](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-%E5%8F%97%E4%BF%A1%E8%80%85%E3%83%BB%E6%89%8B%E6%95%B0%E6%96%99%E3%83%BB%E3%83%AA%E3%83%AC%E3%82%A4%E3%83%A4%E3%83%BC%E3%81%AE%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF)
10. [Fundamentals of contract development](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%B3%E3%83%B3%E3%83%88%E3%83%A9%E3%82%AF%E3%83%88%E9%96%8B%E7%99%BA%E3%81%AE%E5%9F%BA%E7%A4%8E)
    1. [Flow of contract development](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%B3%E3%83%B3%E3%83%88%E3%83%A9%E3%82%AF%E3%83%88%E9%96%8B%E7%99%BA%E3%81%AE%E6%B5%81%E3%82%8C)
    2. [About Solidity](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#solidity%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6)
    3. [About Foundry](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#foundry%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6)
11. [Implementing the pool contract](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%83%97%E3%83%BC%E3%83%AB%E3%82%B3%E3%83%B3%E3%83%88%E3%83%A9%E3%82%AF%E3%83%88%E3%81%AE%E5%AE%9F%E8%A3%85)
    1. [contract test](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%B3%E3%83%B3%E3%83%88%E3%83%A9%E3%82%AF%E3%83%88%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88)
    2. [Exercise: `TornadoCats`Contract interface](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-tornadocats%E3%82%B3%E3%83%B3%E3%83%88%E3%83%A9%E3%82%AF%E3%83%88%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%BC%E3%83%95%E3%82%A7%E3%83%BC%E3%82%B9)
    3. [Exercise: `deposit`Functions](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-deposit%E9%96%A2%E6%95%B0)
    4. [Exercise: `withdraw`Functions](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E6%BC%94%E7%BF%92-withdraw%E9%96%A2%E6%95%B0)
12. [appendix](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E4%BB%98%E9%8C%B2)
    1. [Decentralization of Tornado Cash](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash%E3%81%AE%E9%9D%9E%E4%B8%AD%E5%A4%AE%E9%9B%86%E6%A8%A9%E6%80%A7)
    2. [Tornado Cash operating network and supported currencies](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash%E3%81%AE%E7%A8%BC%E5%83%8D%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%A8%E5%AF%BE%E5%BF%9C%E9%80%9A%E8%B2%A8)
    3. [Tornado Cash main contract address](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash%E3%81%AE%E4%B8%BB%E8%A6%81%E3%82%B3%E3%83%B3%E3%83%88%E3%83%A9%E3%82%AF%E3%83%88%E3%82%A2%E3%83%89%E3%83%AC%E3%82%B9)
    4. [List of major repositories of Tornado Cash](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash%E3%81%AE%E4%B8%BB%E8%A6%81%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E4%B8%80%E8%A6%A7)
    5. [Contracts in Tornado Cash Classic](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash-classic%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%88%E3%83%A9%E3%82%AF%E3%83%88)
        1. [Contract configuration](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E3%82%B3%E3%83%B3%E3%83%88%E3%83%A9%E3%82%AF%E3%83%88%E6%A7%8B%E6%88%90-1)
        2. `[Pairing`Library](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#pairing%E3%83%A9%E3%82%A4%E3%83%96%E3%83%A9%E3%83%AA)
        3. `[Verifier`contract](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#verifier%E3%82%B3%E3%83%B3%E3%83%88%E3%83%A9%E3%82%AF%E3%83%88)
    6. [Tornado Cash Classic Zero-Knowledge Proof Circuit](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash-classic%E3%81%AE%E3%82%BC%E3%83%AD%E7%9F%A5%E8%AD%98%E8%A8%BC%E6%98%8E%E5%9B%9E%E8%B7%AF)
        1. [circuit configuration](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%9B%9E%E8%B7%AF%E6%A7%8B%E6%88%90-1)
        2. `[CommitmentHasher`template](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#commitmenthasher%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88)
        3. `[Withdraw`template](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#withdraw%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88)
        4. `[MerkleTreeChecker`template](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#merkletreechecker%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88)
        5. `[DualMax`template](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#dualmax%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88)
        6. `[HashLeftRight`template](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#hashleftright%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88)
    7. [Circom Lib](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#circomlib)
        1. `[MiMCSponge`template](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#mimcsponge%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88)
        2. `[Pedersen`template](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#pedersen%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88)
        3. `[Num2Bits`template](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#num2bits%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88)
    8. [Tornado Cash Classic Trusted Setup Ceremony](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash-classic%E3%81%AEtrusted-setup-ceremony)
    9. [Governance of Tornado Cash](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash%E3%81%AE%E3%82%AC%E3%83%90%E3%83%8A%E3%83%B3%E3%82%B9)
    10. [Precompiled contracts for zk-SNARK](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#zk-snark%E7%94%A8%E3%81%AE%E3%83%97%E3%83%AA%E3%82%B3%E3%83%B3%E3%83%91%E3%82%A4%E3%83%AB%E6%B8%88%E3%81%BF%E3%82%B3%E3%83%B3%E3%83%88%E3%83%A9%E3%82%AF%E3%83%88)
13. [References](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#%E5%8F%82%E8%80%83%E6%96%87%E7%8C%AE)

---

# Introduction

This material is for yoshi-camp 2022, and the estimated study time is 180 minutes (for yoshi-camp participants: [Introduction Slide](https://translate.google.com/website?sl=auto&tl=en&hl=es&client=webapp&u=https://docs.google.com/presentation/d/1JXbbLLLAxwQKw_ECfV4x_xfMv7vjQknHlrFQ-gDtvOA/edit?usp%3Dsharing) ).

Tornado Cash is famous for being used for money laundering of criminal funds (especially tokens obtained from attacks on blockchain) due to its strong privacy protection, but there are many things that can be learned as a zero-knowledge application. In this hands-on, we aim to learn about zero-knowledge applications and decentralized mixing through the implementation of a simple mixer protocol like Tornado Cash.

# How to proceed hands-on

Before we actually create our own mixer protocol, let me briefly explain Tornado Cash and zero-knowledge proof for those who are not yet familiar with them. After getting a certain amount of what to make, we will actually proceed with development. Basically, development is done in a cycle of "explanation of theory/tools" → "design/implementation". The theoretical knowledge required for a particular design/implementation is explained as soon as possible. Do exercises as appropriate.

# Overview of Tornado Cash

## What is Tornado Cash?

Tornado Cash is a protocol that anonymizes cryptocurrency transfers on the blockchain. Specifically, it is a protocol that anonymizes "to whom it was sent" from the sender's point of view and "from whom it was received" from the receiver's point of view. The amount received is not anonymized. Tornado Cash operates decentralized and cannot change the behavior of already deployed contracts. (See [Tornado Cash Decentralization for](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash%E3%81%AE%E9%9D%9E%E4%B8%AD%E5%A4%AE%E9%9B%86%E6%A8%A9%E6%80%A7) more details.)

Currently, it is deployed on various blockchains, including Ethereum, and supports various ERC-20 tokens besides Ether. ( For more information, see [Tornado Cash's Operating Network and Supported Currencies](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash%E3%81%AE%E7%A8%BC%E5%83%8D%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%A8%E5%AF%BE%E5%BF%9C%E9%80%9A%E8%B2%A8) and [Tornado Cash's Primary Contract Addresses](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/README.md?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp#tornado-cash%E3%81%AE%E4%B8%BB%E8%A6%81%E3%82%B3%E3%83%B3%E3%83%88%E3%83%A9%E3%82%AF%E3%83%88%E3%82%A2%E3%83%89%E3%83%AC%E3%82%B9) .)

## Anonymization mechanism

Anonymization of Tornado Cash is achieved by removing the on-chain connection between the sender address and the receiver address using zero-knowledge proofs.

For example, the flow of using Tornado Cash is as follows.

1. Submit a transaction that sends 1 ETH from the sender address to the Tornado Cash contract. Local stores data called "notes" that are submitted when withdrawing the funds.
2. (If the recipient is someone else, the note is passed off-chain.)
3. Send a transaction with the note attached from the recipient address to the Tornado Cash contract and receive 1 ETH.

Here, zero-knowledge proof technology makes it impossible to obtain the sender address from the note submitted as proof for receiving Ether. From a third party's point of view, deposits and withdrawals are independent, and it is not possible to know the deposit transaction from the withdrawal transaction. ” will not be understood.

## Relayer

In the example above, the recipient address must have Ether in advance for gas to send the transaction. However, using a centralized exchange to prepare that Ether is putting the cart before the horse in terms of privacy. To solve this problem, Tornado Cash has a "Relayer". Relayers send transactions on behalf of recipients in exchange for remittance fees. Privacy is improved thanks to this relayer. You can become a relayer by locking TORN, the governance token.

## mixing

The anonymization method used in Tornado Cash is called mixing. That is why depositing pools are also called mixers.

[https://camo.githubusercontent.com/1a16c6f7b81c87b98a7ad512f10ce8d190846a6477e1f6f175760d545ff38e40/68747470733a2f2f692e6779617a6f2e636f6d2f63323762343638333262343334353333393461316235626138393230356235302e706e67](https://camo.githubusercontent.com/1a16c6f7b81c87b98a7ad512f10ce8d190846a6477e1f6f175760d545ff38e40/68747470733a2f2f692e6779617a6f2e636f6d2f63323762343638333262343334353333393461316235626138393230356235302e706e67)

Your tokens in the pool are completely under your control and cannot be manipulated by third parties (in other words, you have custody).

Tornado Cash can only be made anonymous when there are enough users of the protocol and when they use it correctly. Inappropriate use can break anonymization.

## Inappropriate use that results in loss of anonymity

Inappropriate use, especially the following cases, please be careful.

- There is personally identifiable information in past transaction history without using a relayer
- Time between deposit and withdrawal is too short
- No diversification of recipient addresses, total deposits from sender addresses equal (or nearly equal) to total withdrawals to recipient addresses

The method of estimating the recipient address by statistically analyzing the deposits and withdrawals to the mixer like the latter two methods is called De-mixing.

Other things, unrelated to blockchain, include not using Tor or privacy-preserving VPNs (those that claim to keep no logs).

## Tornado Cash Classic and Tornado Cash Nova

There are two major versions of Tornado Cash. Tornado Cash Classic and Tornado Cash Nova. Tornado Cash Nova is a new version released in December 2021, in contrast to the traditional Tornado Cash called Tornado Cash Classic.

Tornado Cash Classic only allows fixed amount deposits and withdrawals. For example, for Ether, you need to select and use 4 types of pools: 0.1 ETH, 1 ETH, 10 ETH, and 100 ETH. 2.4 If you want to transfer ETH,

- 2 Deposits into a pool of 1 ETH
- 4 deposits to a pool of 0.1 ETH

You have to make a split payment like this. Unlike Tornado Cash Classic, Tornado Cash Nova allows you to transfer any amount.

Tornado Cash Nova also allows transfers within the pool. With Tornado Cash Classic, you need to withdraw from the pool once to complete the transfer. Tornado Cash Nova allows you to transfer any amount of your pool to another address without withdrawing it from the pool. This is called a Shielded Transfer.

In this document, we will implement a simple mixer protocol of “fixed amount deposits and withdrawals” and “no Shielded Transfer” similar to Tornado Cash Classic.

# An overview of zero-knowledge proofs

## What is a zero-knowledge proof?

A zero-knowledge proof is a method of proving a proposition that a person wants to prove to another person without disclosing information (knowledge) other than the truth of the proposition. The "someone" here is called the prover, and the "other person" is called the verifier.

Zero-knowledge proofs have attracted attention for their convenient properties and are used as a privacy protection technology. In addition to protecting privacy, it also has the property that calculation results can be recalculated at high speed, and it is also used as a technology to improve scalability, especially in blockchain.

## Three properties that zero-knowledge proofs should satisfy

Zero-knowledge proofs basically satisfy three properties: completeness, soundness, and zero-knowledge.

### Completeness

If the proposition presented by the prover is true, the verifier must know it to be true.

### Soundness

If the proposition presented by the prover is false, the verifier knows with high probability that it is false.

### Zero-knowledge Property

If the proposition presented by the prover is true, the verifier does not know anything other than the truth.

### Specific example: Anonymous money transfer

Consider these three properties in an anonymous transfer from Alice to Bob.

- **Integrity**
    
    : If Bob sends a valid withdrawal request, the pool must know that the withdrawal request Bob sent is correct.
    
- **Sanity**
    
    : If Bob sends a fraudulent withdrawal request, the pool must know that the withdrawal request Bob sent was incorrect.
    
- **Zero knowledge**
    
    : If Bob sends a valid withdrawal request, the pool has no information other than that the withdrawal request sent by Bob is correct. The information here is, for example, "Who is the depositor?", "When was the deposit made?"
    

## How can a zero-knowledge proof be constructed?

Before we look at the completed zero-knowledge proofs, let's take a moment to think about how a zero-knowledge proof can be constructed.

### problem definition

First, let's briefly define the problem. We have Alice and Bob, each with a secret valuea,band neither of you want to reveal the secret value, but you want to know if the secret values match. What kind of method can be considered in this case?

### bad example

Of course, Alice or Bob cannot send the secret value to the other party, so it would be better to process the secret value somehow. So, the cryptographic hash functionH.Consider the policy of using

AliceH.(a)to Bob, who hasH.(a)=H.(b), it is difficult to inverse the preimage due to the nature of the cryptographic hash function, so the secret value of both sides remains hidden.a,bmatch. Is this a zero-knowledge proof?

The answer is no. Because Alice's hash value is known to Bob. In addition to the information that "Alice and Bob's secret values match", the information "Alice's hash value" is leaked, and zero knowledge is not satisfied.

### good example

So how can we prove this proposition so that it satisfies zero knowledge?

Before explaining it, let's first transform the problem into another manageable form. This time Alice is the prover and Bob is the verifier.x"Knowing that" is a zero-knowledge proof. This proposition ispA finite field with prime𝕡F.pIn "Alicegx(modsp)ofxcan be translated as "that you know".gteeth𝕡F.punder thegWhenpis shared by two people.

Like hash functions,gxif you sendxEven if it is difficult to obtain (discrete logarithm problem), it does not satisfy zero knowledge.

To solve this problem, you should follow these steps:

1. Alice is a temporary random number
    
    r
    
    to generate this
    
    r
    
    teeth,
    
    q
    
    of
    
    gq=1
    
    The smallest natural number such that
    
    F.p
    
    in
    
    g
    
    as the order of
    
    0
    
    from
    
    q−1
    
    Select within the range of and
    
    c=gr
    
    to Bob.
    
2. Bob is a temporary random number
    
    e
    
    of
    
    0
    
    from
    
    q−1
    
    and send it to Alice.
    
3. Alice is
    
    z=r+ex
    
    to Bob.
    
4. Bob is
    
    gz=cye
    
    is true.
    
    gz
    
    teeth,
    
    gz=gr+ex=gr⋅(gx)e=cye
    
    and if Alice has a secret value
    
    x
    
    This will match if you know
    

This procedure is called the Schnorr protocol, and it satisfies the three properties introduced earlier. It would be a good idea to check that you are actually satisfied.

## Non-interactive zero-knowledge proof

The Schnorr protocol is called an interactive zero-knowledge proof because, as you can see, Alice and Bob are talking to each other. However, this interactive nature is very incompatible with distributed systems, especially blockchain smart contracts. Sending a transaction, executing the transaction in a block, seeing the results of that execution, sending the transaction again, and so on, just thinking about it makes me sick. Also, it cannot handle the case where it must be completed in one transaction in the first place.

Non-interactive zero-knowledge proofs exist to solve such challenges. Using pairings and using hash functions, interactive zero-knowledge proofs can be transformed into non-interactive zero-knowledge proofs. In this hands-on, we use a zk-SNARK type of non-interactive zero-knowledge proof, which uses pairing.

## zk-SNARK

Zero-Knowledge Succinct Non-Interactive Argument of Knowledge, zk-SNARK for short, is one of the categories of non-interactive zero-knowledge proofs. In addition to completeness, soundness, and zero knowledge, it also has simplicity (Succinct Property), which is where the name comes from. Collectively, protocols that are zk-SNARKs are called zk-SNARKs.

Conciseness is the property that proofs are of constant size. This is very compatible with blockchain. Blockchain transaction fees increase with the size of the data processed. Simplicity ensures that the fee remains constant, no matter how complicated the proof is.

In this hands-on, we will use a zk-SNARK called [Groth16](https://translate.google.com/website?sl=auto&tl=en&hl=es&client=webapp&u=https://eprint.iacr.org/2016/260.pdf) announced by Jens Groth in 2016 .

# Environment

Now that I have shared the minimum knowledge about Tornado Cash and zero-knowledge proofs, I would like to create my own mixer protocol. Let's start by building the environment. There are various tools that need to be installed, but we have prepared a [Dockerfile](https://github-com.translate.goog/minaminao/tornado-cats/blob/main/Dockerfile?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp) that can be used to install them all at once. If the build fails, please refer to the Dockerfile and install each tool on the native OS. Basically, we proceed by developing on the native OS and executing the application in a container.

Execute the following command under this repository. A Docker image is built, and a Docker container is created and started.

`docker build . -t tornado-cats
docker create --name tornado-cats -v $(pwd):/home/cat/tornado-cats -it tornado-cats
docker start -ai tornado-cats`

`docker create-v`By specifying the option in the command, the tornado-cats repository files will be mounted in the tornado-cats directory under the user cat's home directory. Data is exchanged via the mounted directory. If you have logged out `docker start -ai tornado-cats`, please try again. `docker run`is not used because the environment cannot be inherited. If you want to build again and recreate the container, do `docker rm tornado-cats`so.

# Basics of Zero-Knowledge Proof Circuits

## What is a circuit

In order to implement the mixer protocol, we have to write a program to generate zero-knowledge proofs. Such a program is called a circuit. A circuit is a transformation of a proposition so that it can be easily handled by a computer.

## What is Circom

I use Circom as a tool for creating circuits. Circom is a compiler that converts circuits written in the high-level Circom language, which is easy for humans to understand, into low-level circuits, which are easy for computers to understand. For example, it is similar to the hardware description language (HDL) used to describe electrical circuits.

Circom used to be written in JavaScript, but now it's in Rust. The current Circom is called Circom 2 and the previous one is called Circom 1 for contrast. Circom 1 and Circom 2 also have different language specifications. Circom 1 is still maintained, but will be deprecated in the future.

Tornado Cash also uses Circom. Tornado Cash Classic was developed using Circom 1, but in this hands-on we will use the latest Circom 2.

## Example Circuit: Factorization

Let's take a quick look at the Circom circuit. For example, if you want a zero-knowledge proof that ``33 can be decomposed into two factors,'' the following circuit is conceivable.

`pragma circom 2.1.2;

// 回路の定義
template Multiplier2 () {  

   // シグナルの宣言  
   signal input a;  
   signal input b;  
   signal output c;  

   // 制約
   c <== a * b;  
}

// インスタンス化
component main = Multiplier2();`

It can only be decomposed into factors (including 1),33=1⋅33Unfortunately, in RSA encryption, it is possible to decompose liken=pqofp,qIt cannot be used as it is for applications such as zero-knowledge proof that you know. It is a simple circuit and suitable for explaining the language specification, so I will explain it without making any particular changes.

First, the `prgram`instruction specifies the version of the Circom compiler. If you use a function that does not comply with the language specification of the specified version, an error will occur. `2.1.12`This example specifies the latest version .

Next, `template`we define the template for the circuit. A template is like a blueprint that defines a new circuit. As will be explained later, `component`it is instantiated and used. This example `Multiplier2`defines a circuit named

`template`Inside the , we first declare the signal. A signal is used for input/output of a circuit, etc.F.pis an element of `input`is an input signal if `output`specified, and an output signal if is specified. If nothing is specified, it will be called an intermediate signal. `a`Signals defines an input signal and an `b`output signal in this example `c`.

Constraints are written after the signal declaration. Constraints are statements that specify conditions between signals. It can be described using `<==`operators and operators. `==>`Note that the constraint must be a quadratic or lower function of the signal. In other words, `A`if `B`there `C`are three signals , `A * B + C`, is allowed, `A * B * C`but is not. In this example, `c`we `a`assume `b`that is multiplied by . `a * b ==> c`It is also good as

Finally, `component`we instantiate the circuit from the template. To run the circuit, an initial component is required, and that component's name is by default `main`. In this example, the instantiated `Multiplier2()`is executed.

## Compiling the circuit

Now let's actually compile this circuit. First, `circuits/multiplier2`create a directory and move to it. Copy and paste the code above `multiplier2.circom`to create a file called Any directory can be used to place the circuit, but in this hands-on, we will `circuits`proceed on the premise that we will work together.

`muliplier2.circom`You can compile by running the following command :

`circom multiplier2.circom --r1cs --wasm --sym --c`

Each option has the following meaning:

- `-r1cs`
    
    : Generate the R1CS (described later) file of the circuit.
    
- `-wasm`
    
    : Generate WebAssembly files, etc. required for generating Witness (described later).
    
- `-sym`
    
    : Generates files needed for constraint debugging.
    
- `-c`
    
    : Generates the C++ code, etc. required to generate the witness.
    

I expect the result to look like this: `Everything went okay`is displayed, it is successful.

`$ circom multiplier2.circom --r1cs --wasm --sym --c
template instances: 1
non-linear constraints: 1
linear constraints: 0
public inputs: 0
public outputs: 1
private inputs: 2
private outputs: 0
wires: 4
labels: 4
Written successfully: ./multiplier2.r1cs
Written successfully: ./multiplier2.sym
Written successfully: ./multiplier2_cpp/multiplier2.cpp and ./multiplier2_cpp/multiplier2.dat
Written successfully: ./multiplier2_cpp/main.cpp, circom.hpp, calcwit.hpp, calcwit.cpp, fr.hpp, fr.cpp, fr.asm and Makefile
Written successfully: ./multiplier2_js/multiplier2.wasm
Everything went okay, circom safe`

## Rank 1 Constraint System (R1CS)

The Rank 1 Constraint System (R1CS) is a sequence of constraints that the proofs generated by the circuit must satisfy. More specifically, R1CS is a sequence of three vectors(a,b,c)and the solution issand(s⋅a)(s⋅b)−s⋅c=0is established.

`muliplier2.r1cs`Let's take a look at what's actually generated this time . The R1CS file is a binary file, but the `snarkjs r1cs info`command can output R1CS meta information, and the `snarkjs r1cs print`command can output R1CS.

`$ snarkjs r1cs info
 multiplier2.r1cs
[INFO]  snarkJS: Curve: bn-128
[INFO]  snarkJS: # of Wires: 4
[INFO]  snarkJS: # of Constraints: 1
[INFO]  snarkJS: # of Private Inputs: 2
[INFO]  snarkJS: # of Public Inputs: 0
[INFO]  snarkJS: # of Labels: 4
[INFO]  snarkJS: # of Outputs: 1`

`$ snarkjs r1cs print multiplier2.r1cs
[INFO]  snarkJS: [ 21888242871839275222246405745257275088548364400416034343698204186575808495616main.a ] * [ main.b ] - [ 21888242871839275222246405745257275088548364400416034343698204186575808495616main.c ] = 0`

Now, with constraints, the `c <== 2 * a * b + 1337;`result is:

`$ snarkjs r1cs print multiplier2.r1cs
[INFO]  snarkJS: [ 21888242871839275222246405745257275088548364400416034343698204186575808495615main.a ] * [ main.b ] - [ 1337 +21888242871839275222246405745257275088548364400416034343698204186575808495616main.c ] = 0`

You can see that the coefficient is doubled and a constant of 1337 is added.

## Witness calculation

To create a zero-knowledge proof, we need to determine real-value assignments for the signals that satisfy all the constraints of the circuit. The set of signal value assignments is called a witness.

Let's look at a concrete example. If the values of the input signals are known, the calculation of the intermediate and output signals is straightforward. This time, we want to prove that 33 can be factorized, so let's use `a = 3`, as the input signal. Create a file `b = 11`like this:`input.json`

`{"a": "3", "b": "11"}`

in JavaScript253Use strings instead of numbers for signal values due to the lack of precision for larger integers.

Let's use this `input.json`to calculate the witness. Please run the following command:

`node multiplier2_js/generate_witness.js multiplier2_js/multiplier2.wasm input.json witness.wtns`

`witness.wtns`Now you have created a Witness file using WebAssembly . `a = 3`Data , `b = 11`, `c = 33`are recorded in this file . It means that we have found one of the assignments of the values of all signals when 33 can be factored.

`wtns`The file is a binary file, `snarkjs wtns export json`but you can see the contents with the command.

`$ snarkjs wtns export json witness.wtns && cat witness.json
[
 "1",
 "33",
 "3",
 "11"
]`

This JSON file contains the wire calculation results. As an image of a wire, it is a step from input to output. A Witness is a collection of wire values, a snapshot of intermediate values. It was displayed in the execution result of a while ago, but this is the substance `snarkjs r1cs info`.`[INFO] snarkJS: # of Wires: 4`

The meaning of each number in the above file is as follows.

- `1`
    
    : just a constant
    
- `33`
    
    : public output
    
- `311`
    
    ,
    
    : private input
    

## Setting up a zero-knowledge proof

Witness is required, but in order to generate a zero-knowledge proof, it is necessary to generate a key for the zero-knowledge proof.

### Trusted Setup

Trusted Setup is required to generate keys for zk-SNARKs. A Trusted Setup, as the name suggests, is a setup that trusts a third party. However, in a protocol that emphasizes decentralization such as Tornado Cash, we do not want to trust a specific third party, so Multi-Party Computation (MPC) executes Trusted Setup in a decentralized manner. This is called Trusted Setup Ceremony or MPC Ceremony.

### Trusted Setup Ceremony

Tornado Cash held a Trusted Setup Ceremony in May 2020 with over 1000 accounts participating. It is impossible to forge a zero-knowledge proof unless all of the accounts participating in this Trusted Setup Ceremony betray. Conversely, if even one person takes the right action, it is safe.

Circom uses a zk-SNARK protocol called Groth16. Groth16 requires a Trusted Setup for each circuit. This Trusted Setup is divided into two stages, called Perpetual Powers of Tau Ceremony. The first stage is a circuit independent setup and the second stage is a circuit dependent setup.

Tornado Cash's Trusted Setup Ceremony was done using [zkUtil](https://github-com.translate.goog/poma/zkutil?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp) , but this hands-on uses snarkjs.

### Phase 1

`snarkjs powersoftau new bn128 12 pot12_0000.ptau -v`

`$ snarkjs powersoftau new bn128 12 pot12_0000.ptau -v
[DEBUG] snarkJS: Calculating First Challenge Hash
[DEBUG] snarkJS: Calculate Initial Hash: tauG1
[DEBUG] snarkJS: Calculate Initial Hash: tauG2
[DEBUG] snarkJS: Calculate Initial Hash: alphaTauG1
[DEBUG] snarkJS: Calculate Initial Hash: betaTauG1
[DEBUG] snarkJS: Blank Contribution Hash:
		786a02f7 42015903 c6c6fd85 2552d272
		912f4740 e1584761 8a86e217 f71f5419
		d25e1031 afee5853 13896444 934eb04b
		903a685b 1448b755 d56f701a fe9be2ce
[INFO]  snarkJS: First Contribution Hash:
		9e63a5f6 2b96538d aaed2372 481920d1
		a40b9195 9ea38ef9 f5f6a303 3b886516
		0710d067 c09d0961 5f928ea5 17bcdf49
		ad75abd2 c8340b40 0e3b18e9 68b4ffef`

`snarkjs powersoftau contribute pot12_0000.ptau pot12_0001.ptau --name="First contribution" -v`

`$ snarkjs powersoftau contribute pot12_0000.ptau pot12_0001.ptau --name="First contribution" -v
Enter a random text. (Entropy): ***
[DEBUG] snarkJS: Calculating First Challenge Hash
[DEBUG] snarkJS: Calculate Initial Hash: tauG1
[DEBUG] snarkJS: Calculate Initial Hash: tauG2
[DEBUG] snarkJS: Calculate Initial Hash: alphaTauG1
[DEBUG] snarkJS: Calculate Initial Hash: betaTauG1
[DEBUG] snarkJS: processing: tauG1: 0/8191
[DEBUG] snarkJS: processing: tauG2: 0/4096
[DEBUG] snarkJS: processing: alphaTauG1: 0/4096
[DEBUG] snarkJS: processing: betaTauG1: 0/4096
[DEBUG] snarkJS: processing: betaTauG2: 0/1
[INFO]  snarkJS: Contribution Response Hash imported: 
		09297d56 9259c5f9 033074b5 42af23ca
		3ee3102e 314eaf3a 5e77543d b4ce3c7e
		cce64587 1c9a86b5 0880c878 379d1e6d
		65ca23a8 fddc7b2f 0cf3f954 0e9a1a87
[INFO]  snarkJS: Next Challenge Hash: 
		f4e97b7e ef159686 4b7eec61 d09167a0
		d9d9e693 c2cfe145 6222b13b 72ad0bc0
		2f6cc1b6 a9a61b6f fc358d51 abe05e2e
		32ce0164 2b8ec1b9 ddeba568 7557488c`

### Phase 2

`snarkjs powersoftau prepare phase2 pot12_0001.ptau pot12_final.ptau -v`

The output is long, so I'll omit it.

`snarkjs groth16 setup multiplier2.r1cs pot12_final.ptau multiplier2_0000.zkey`

`$ snarkjs groth16 setup multiplier2.r1cs pot12_final.ptau multiplier2_0000.zkey
[INFO]  snarkJS: Reading r1cs
[INFO]  snarkJS: Reading tauG1
[INFO]  snarkJS: Reading tauG2
[INFO]  snarkJS: Reading alphatauG1
[INFO]  snarkJS: Reading betatauG1
[INFO]  snarkJS: Circuit hash: 
		adae36e7 dc98ebda c5114789 c89889ee
		a93f0b06 027201e1 74df3d5c 52fe3b89
		c379661e bdf28d88 0a217302 bed570c6
		55c5ffc1 51f6bf7b 09008076 4d4cf201`

`snarkjs zkey contribute multiplier2_0000.zkey multiplier2_0001.zkey --name="1st Contributor Name" -v`

`$ snarkjs zkey contribute multiplier2_0000.zkey multiplier2_0001.zkey --name="1st Contributor Name" -v 
Enter a random text. (Entropy): ***
[DEBUG] snarkJS: Applying key: L Section: 0/2
[DEBUG] snarkJS: Applying key: H Section: 0/4
[INFO]  snarkJS: Circuit Hash: 
		adae36e7 dc98ebda c5114789 c89889ee
		a93f0b06 027201e1 74df3d5c 52fe3b89
		c379661e bdf28d88 0a217302 bed570c6
		55c5ffc1 51f6bf7b 09008076 4d4cf201
[INFO]  snarkJS: Contribution Hash: 
		b384c86d d68984de e245062e 28128f44
		89690435 cde637ef 524a86f7 0a6f52ee
		1673e474 ee23fa35 1cc167f5 a5f811c8
		d47b660c 79e4c578 a49b63b3 3b843bd8`

`snarkjs zkey export verificationkey multiplier2_0001.zkey verification_key.json`

## Generating Zero-Knowledge Proofs

`snarkjs groth16 prove multiplier2_0001.zkey witness.wtns proof.json public.json`

## Validation of zero-knowledge proofs

`snarkjs groth16 verify verification_key.json public.json proof.json`

`$ snarkjs groth16 verify verification_key.json public.json proof.json
[INFO]  snarkJS: OK!`

`proof.json`is correct and 33 can be factored.

## Exercise: Multiplier with 3 Input Signals

Please refer to the multiplier with two input signals and make a multiplier with three input signals. If you have the time `multiplier2`, try making something that uses the one you created earlier.

- Tips

## Exercise: Multiplier with N Input Signals

I made a multiplier with 3 input signals. Generalize to make a multiplier with N input signals.

## Exercise: A circuit that checks if an input signal is true or false

Create a circuit that takes an input signal and returns it if the signal is 0 or 1. Name the template `binaryCheck`as

## Exercise: Logical AND Circuits

`Multiplier2`Use and `binaryCheck`to create a logical AND circuit that takes two input signals.

## Exercise: N-Input Logical AND Circuit (Optional)

`Multiplier2`Use and `binaryCheck`to create a logical AND circuit that takes N input signals.

# Configuration of Homebrew Mixer Protocol

## Basic policy

Basically, make it similar to the configuration of Tornado Cash Classic. However, the Tornado Cash Classic implementation was first released three years ago, and although there are some updates, there are old parts in the system configuration and tool versions. I try not to resemble such parts as much as possible. Also, to focus on the essence of mixing, we will only implement a pool of Ether and not a pool of ERC20 tokens.

## Exercise: Designing a Mixer Protocol

Consider what kind of protocol design should be used to make Ether anonymous transfers using zero-knowledge proofs. Please diagram the relationship of each component (user, pool contract, program that generates zero-knowledge proof, etc.) at the time of deposit and withdrawal in chronological order. Pay particular attention to what processing is done on-chain/off-chain.

## Overall structure of the protocol

## Contract configuration

| contract | explanation |
| --- | --- |
| TornadoCats.sol | The contract that manages the pool. Deposit and withdrawal interface. |
| MerkleTreeWithHistory.sol | A contract for the MiMC Merkle tree that holds the root history. |
| Verifier.sol | A contract that validates zero-knowledge proofs. A pairing library is also defined. |

## circuit configuration

| circuit | explanation |
| --- | --- |
| merkleTree.circom | The circuit of the MiMC Merkle tree |
| withdraw.circom | Withdrawal circuit |

# deposit and withdrawal design

In the previous chapter, we learned how to create a zero-knowledge proof circuit. Now, how should we design deposits and withdrawals to the pool contract? In particular, it is important to satisfy the following properties.

1. There is no connection between the deposit address and the withdrawal address
2. Don't let the pool lose money by making double withdrawals

An attack that results in double withdrawals because property 2 is not satisfied is generally called a Double-Spending Attack.

## Exercise: Designing a Deposit/Withdrawal Operation

Consider a deposit/withdrawal operation that satisfies the above properties.

## Bad design example

For example, consider the following design. a data structureT.and a certain hash function isH.and let a secret random number beswill do. Any data structure can be used as long as it can be registered/deleted, but for example, imagine a Merkle tree where data can be stored in the leaves. Record whether the data has been deleted or not.

operation

- payment:
    
    H.(s)
    
    of
    
    T.
    
    operations (so-called commitments) that register to
    
- Withdrawal: "
    
    s
    
    Prove zero-knowledge that you know
    
    H.(s)
    
    operation to delete
    

How about this? Property 2 is satisfied, but property 1 is clearly not satisfied. with deposits and withdrawalsH.(s)Since we use , deposits and withdrawals are tied.

## Bad design example 2

In the previous design example,H.(s)It was a problem to register / delete directly. Then the data structureT.that you are registered withH.(s)What if we decide to do a zero-knowledge proof without directly using For example, consider the following design.

operation

- payment:
    
    H.(s)
    
    of
    
    T.
    
    Operation to be registered in
    
- Withdrawal: "
    
    s
    
    is a leaf that knows
    
    H.(s)
    
    But
    
    T.
    
    An operation to prove zero-knowledge that
    

How about this? Property 1 seems to be satisfied. with zero knowledgesandH.(s)Deposits and withdrawals are not tied because it is impossible to know However, property 2 is not satisfied.H.(s)will not be deleted, so you will be able to make double withdrawals.

## good design example

In the previous design example, it was not possible to tie a withdrawal to a cash receipt, which was nice, but the problem was that it was not possible to know if one withdrawal came from the same commitment as another. For example, consider the following design. It introduces a new random number called a nullifier. NullifiernAs another Merkle treeT.nPrepare Of this timeT.Imagine a normal Merkle tree.

operation

- payment:
    
    H.(n+s)
    
    of
    
    T.
    
    Operation to be registered in
    
- Withdrawal: "
    
    s
    
    When
    
    n
    
    know
    
    H.(n+s)
    
    But
    
    T.
    
    zero-knowledge proof that it is registered in
    
    H.(n)
    
    of
    
    T.n
    
    Operation to be registered in
    

With the introduction of Nullifier, it is no longer possible to withdraw twice for a given deposit. Now we can satisfy both property 1 and property 2.

## Selection of algorithms and data structures

The rough design above is fine, but the calculation of zero-knowledge proof is heavy, and if the amount of calculation of the contract verification process is large, a high fee will be incurred. Therefore, I would like to choose hash functions and Merkle trees that are computationally compatible with zero-knowledge proofs.

This time, we use Pedersen hash for hash function and MiMC Merkle tree for Merkle tree. I will briefly explain each.

## What is a Pedersen Hash

Pedersen hash is a hash function that can be calculated at high speed with a zero-knowledge proof circuit. Commonly used cryptographic hash functions such as SHA-256 produce very different outputs given slightly different inputs (called the avalanche effect). The Pedersen hash prioritizes fast computation and does not have this property.

## What is the MiMC Merkle Tree?

First of all, there is a MiMC hash as a premise. MiMC hash is one of the hash functions designed to reduce the number of multiplications. It comes from "Minimal Multiplicative Complexity". MiMC hashes designed in this way are useful because of the high cost of multiplication in zero-knowledge proofs.

A MiMC Merkle tree is, as the name suggests, a Merkle tree that uses MiMC hashes.

# Implementation of withdrawal circuit

Let's implement it as soon as the policy of the withdrawal circuit is fixed to some extent.

## Exercise: Defining Signals and Creating Components

`withdraw.circom`will be created. `Withdraw`Create a template to define your signal. Also instantiate the template to `main`create the component.

## Exercise: Check Nullifiers

Add a process to check if the given nullifier is correct.

## Exercise: Checking the MiMC Merkle Tree

Add a process to check if the correct MiMC Merkle tree can be constructed from the given commitment, path and root.

## Exercise: Checking Recipients, Fees, and Relayers

These must be incorporated into the circuit constraints so that receivers, fees and relayers cannot be forged. Please add that process.

# Fundamentals of contract development

Before we start implementing pool contracts, let me explain what you need to know to develop contracts.

## Flow of contract development

In this hands-on, we will develop the contract according to the following flow.

1. `src`
    
    Implement the contract on your directory.
    
2. Run test ( `forge test`
    
    ).
    
3. If an error occurs, return to 1.

Since we have already implemented the tests, the goal is to implement a contract that passes all the tests.

## About Solidity

If you are unsure about Solidity knowledge, please refer to the [Solidity document (Japanese) .](https://translate.google.com/website?sl=auto&tl=en&hl=es&client=webapp&u=https://solidity-ja.readthedocs.io/ja/latest/) (The translation is centered on minaminao. Some parts are not yet translated, but the content covered in this hands-on is covered.)

## About Foundry

No special knowledge of Foundry is required, but if you have any trouble, please refer to the [official documentation .](https://translate.google.com/website?sl=auto&tl=en&hl=es&client=webapp&u=https://book.getfoundry.sh/)

# Implementing the pool contract

## contract test

Now let's implement the pool contract. Run the following command to test the contract. If all the tests pass, your implementation is correct, so aim to pass the tests.

`forge test -vvv`

## Exercise: `TornadoCats`Contract interface

`TornadoCats`is a contract that users directly operate when making deposits and withdrawals. First , create the `deposit`function and `withdraw`the interface part of the function (the contents of the function are empty).

`deposit`function

- argument
    - `bytes32 commitment`
- Return value
    - none

`withdraw`function

- argument
    - `bytes calldata proof`
    - `bytes32 root`
    - `bytes32 nullifierHash`
    - `address payable recipient`
    - `address payable relayer`
    - `uint256 fee`
- Return value
    - none

## Exercise: `deposit`Functions

`deposit`Create the body of the function.

Specifically, implement the following processing.

- Revert if commitment `commitment`
    
    was already registered
    
- Revert if the remittance amount does not meet the `msg.valuedenomination`
    
    remittance unit
    
- `commitment`
    
    Insert Commitment in Merkle Tree
    
- Register Commitment
- `Deposit`
    
    event firing
    

## Exercise: `withdraw`Functions

`withdraw`make a function

Specifically, implement the following processing.

- `denomination`
    
    Revert if fees exceed
    
- Revert if the note has already been consumed
- Revert if Merkle route is not in route history
- Verify if the proof `proof`
    
    is correct and revert if incorrect
    
- Record notebook consumption
- Withdrawal processing to recipient address
- Processing fee remittance to relayer
- `Withdrawal`
    
    event firing
    

# appendix

## Decentralization of Tornado Cash

Tornado Cash contracts are designed to be immutable and will not be changed or upgraded.

In the first place, the bytecode of deployed contracts is usually immutable in Ethereum. There are three main ways to change the behavior of a contract.

- `CREATE2SELFDESTRUCT`
    
    Deploy a contract with opcode,
    
    destroy the contract with , and deploy another contract again.
    
- A protocol parameter change function is added in advance to change the parameters.
- A pseudo-upgrade is realized using a proxy contract.

To change the behavior of the contract in any way after such deployment, the functionality must be included in the contract bytecode before deployment. Tornado Cash used to have the ability to change protocol parameters, but it is no longer possible. This is because we set the account with modification rights to a zero address that no one owns. Also, it's not possible to upgrade because I'm not using a proxy.

## Tornado Cash operating network and supported currencies

| network name | Supported Currencies (Symbols) |
| --- | --- |
| Ethereum | ETH, DAI, cDAI, USDC, USDT, WBTC |
| BNB Smart Chain | BNB |
| Polygon | MATIC |
| Gnosis Chain | xDAI |
| Avalanche | AVAX |
| Optimism | ETH |
| Arbtirum | ETH |

## Tornado Cash main contract address

| contract address | explanation |
| --- | --- |
| 0x12D66f87A04A9E220743712cE6d9bB1B5616B8Fc | 0.1 ETH Pool |
| 0x47CE0C6eD5B0Ce3d3A51fdb1C52DC66a7c3c2936 | 1 ETH Pool |
| 0x910Cbd523D972eb0a6f4cAe4618aD62622b39DbF | 10 ETH pool |
| 0xA160cdAB225685dA1d56aa342Ad8841c3b53f291 | 100 ETH pool |
| 0xD4B88Df4D29F5CedD6857912842cff3b20C8Cfa3 | 100 DAI Pool |
| 0xFD8610d20aA15b7B2E3Be39B396a1bC3516c7144 | 1,000 DAI Pool |
| 0x07687e702b410Fa43f4cB4Af7FA097918ffD2730 | 10,000 DAI Pool |
| 0x22aaA7720ddd5388A3c0A3333430953C68f1849b | 5,000 cDAI pool |
| 0xBA214C1c1928a32Bffe790263E38B4Af9bFCD659 | 50,000 cDAI pool |
| 0x03893a7c7463AE47D46bc7f091665f1893656003 | 50,000 cDAI pool |
| 0x2717c5e28cf931547B621a5dddb772Ab6A35B701 | 500,000 cDAI pool |
| 0xD21be7248e0197Ee08E0c20D4a96DEBdaC3D20Af | 5,000,000 cDAI pool |
| 0x4736dCf1b7A3d580672CcE6E7c65cd5cc9cFBa9D | 100 USDC Pool |
| 0xd96f2B1c14Db8458374d9Aca76E26c3D18364307 | 1,000 USDC Pool |
| 0x169AD27A470D064DEDE56a2D3ff727986b15D52B | 100 USDT pool |
| 0x0836222F2B2B24A3F36f98668Ed8F0B38D1a872f | 1,000 USDT Pool |
| 0x178169B423a011fff22B9e3F3abeA13414dDD0F1 | 0.1 WBTC Pool |
| 0x610B717796ad172B316836AC95a2ffad065CeaB4 | 1 WBTC pool |
| 0xbB93e510BbCD0B7beb5A853875f9eC60275CF498 | 10 WBTC Pool |

## List of major repositories of Tornado Cash

It became an archive after the organization was banned and released on GitHub, but there is a repository at [https://github.com/tornadocash .](https://github-com.translate.goog/tornadocash?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp) The latest version is available at [https://development.tornadocash.community/tornadocash](https://translate.google.com/website?sl=auto&tl=en&hl=es&client=webapp&u=https://development.tornadocash.community/tornadocash) (unverified).

| repository | explanation |
| --- | --- |
| tornado-core | Tornado Cash Classic |
| tornado-nova | Tornado Cash Nova |
| tornado-cli | Tornado Cash CLI |
| tornado-relayer | Relay client for Tornado Cash Classic |
| tornado-pool-relayer | Tornado Cash Nova relay client |
| torn-token | Governance token TORN contract |
| tornado-governance | Tornado Cash Governance Contract |
| tornado-anonymity-mining | Anonymity Mining Contracts and Circuits |
| tornado-classic-ui | Tornado Cash Classic UI |
| ui-minified | Tornado Cash Classic UI (minified) |
| nova-ui-minified | Tornado Cash Nova UI (minified) |
| docs | Tornado Cash Documentation |

## Contracts in Tornado Cash Classic

### Contract configuration

| contract | explanation |
| --- | --- |
| Tornado.sol | An abstract contract that manages the pool. It defines common processing and interfaces for deposits and withdrawals. |
| ETHTornado.sol | Pool contract for Ether. Tornadoinherited. |
| ERC20Tornado.sol | ERC20 pool contract. Tornadoinherited. |
| cTornado.sol | Pool contract for Compound's cTokens. ERC20Tornadoand specialized to transfer COMP tokens to the Tornado Cash governance contract. |
| MerkleTreeWithHistory.sol | Contracts for the MiMC Merkle tree. |
| Verifier.sol | A contract that validates zero-knowledge proofs. A pairing library is also defined. |

### `Pairing`Library

Ethereum has precompiled contracts for pairing. It is assumed that precompiled contracts `STATICCALL`use opcodes, but since it is troublesome to use members in Solidity every time, a library has been created `staticcall`that combines precompiled contract wrapper functions and frequently used processes. `Pairing`increase.

`PRIME_Q`:`21888242871839275222246405745257275088696311157297823662689037894645226208583`

`G1Point`and `G2Point`two structs are defined.

  `struct G1Point {
    uint256 X;
    uint256 Y;
  }`

  `struct G2Point {
    uint256[2] X;
    uint256[2] Y;
  }`

**Function list** :

| Function signature (including argument names) | return type | explanation |
| --- | --- | --- |
| negate(G1Point memory p) | G1Point memory |  |
| plus(G1Point memory p1, G1Point memory p2) | G1Point memory |  |
| scalar_mul(G1Point memory p, uint256 s) | G1Point memory |  |
| pairing(G1Point memory a1, G2Point memory a2, G1Point memory b1, G2Point memory b2, G1Point memory c1, G2Point memory c2, G1Point memory d1, G2Point memory d2) | bool | Check pairing |

`plus`, `scalar_mul`, `pairing`uses a precompiled contract that computes on the elliptic curve alt_bn128. These have been added below.

- [EIP-196: Precompiled contracts for addition and scalar multiplication on the elliptic curve alt_bn128](https://translate.google.com/website?sl=auto&tl=en&hl=es&client=webapp&u=https://eips.ethereum.org/EIPS/eip-196)
- [EIP-197: Precompiled contracts for optimal ate pairing check on the elliptic curve alt_bn128](https://translate.google.com/website?sl=auto&tl=en&hl=es&client=webapp&u=https://eips.ethereum.org/EIPS/eip-197)

Gas costs have been updated in [EIP-1108: Reduce alt_bn128 precompile gas costs .](https://translate.google.com/website?sl=auto&tl=en&hl=es&client=webapp&u=https://eips.ethereum.org/EIPS/eip-1108)

| name * | address | Consumed gas | input | output | explanation |
| --- | --- | --- | --- | --- | --- |
| alt_bn128_add | 0x06 | 150 | x1, y1, x2,y2 | x,y |  |
| alt_bn128_mul | 0x07 | 6000 | x1, y1,s | x,y |  |
| alt_bn128_pairing_check | 0x08 | 34000 * k + 45000 | x1, y1, x3, x2, y3,y2 | success |  |

`pairing`In the function, `e(p1[0], p2[0]) * .... * e(p1[n], p2[n]) == 1`do a check for For example, `pairing([P1(), P1().negate()], [P2(), P2()])`is `true`. where , `P1`is `P2`a point such as

    `function P1() internal returns (G1Point) {
        return G1Point(1, 2);
    }
    function P2() internal returns (G2Point) {
        return G2Point(
            [11559732032986387107991004021392285783925812861821192530917403151452391805634,
             10857046999023057135944570762232829481370756359578518086990519993285655852781],
            [4082367875863433681332203403145435568316851327593401208105741076214120093531,
             8495653923123431417604973247489272438418190587263600148770280649306958101930]
        );
    }`

### `Verifier`contract

**Function list** :

| Function signature (including argument names) | return type | explanation |
| --- | --- | --- |
| verifyingKey() | VerifyingKey memory | pureA function that returns the verification key embedded in the contract . |
| verifyProof(bytes memory proof, uint256[6] memory input) | bool | Verify proof. |

## Tornado Cash Classic Zero-Knowledge Proof Circuit

### circuit configuration

| circuit | explanation |
| --- | --- |
| merkleTree.circom |  |
| withdraw.circom |  |

### `CommitmentHasher`template

`// computes Pedersen(nullifier + secret)
template CommitmentHasher() {
    signal input nullifier;
    signal input secret;
    signal output commitment;
    signal output nullifierHash;

    component commitmentHasher = Pedersen(496);
    component nullifierHasher = Pedersen(248);
    component nullifierBits = Num2Bits(248);
    component secretBits = Num2Bits(248);
    nullifierBits.in <== nullifier;
    secretBits.in <== secret;
    for (var i = 0; i < 248; i++) {
        nullifierHasher.in[i] <== nullifierBits.out[i];
        commitmentHasher.in[i] <== nullifierBits.out[i];
        commitmentHasher.in[i + 248] <== secretBits.out[i];
    }

    commitment <== commitmentHasher.out[0];
    nullifierHash <== nullifierHasher.out[0];
}`

`nullifier`is `secret`input `commitment`and `nullifierHash`output is . `nullifier`and `secret`are first `Num2Bits`converted to 248-bit. Then, `Pedersen`using a circuit, `nullifier`and `nullifier + secret`are Pedersen hashed. `nullifierHash`, respectively `commitment`.

### `Withdraw`template

`// Verifies that commitment that corresponds to given secret and nullifier is included in the merkle tree of deposits
template Withdraw(levels) {
    signal input root;
    signal input nullifierHash;
    signal input recipient; // not taking part in any computations
    signal input relayer;  // not taking part in any computations
    signal input fee;      // not taking part in any computations
    signal input refund;   // not taking part in any computations
    signal private input nullifier;
    signal private input secret;
    signal private input pathElements[levels];
    signal private input pathIndices[levels];

    component hasher = CommitmentHasher();
    hasher.nullifier <== nullifier;
    hasher.secret <== secret;
    hasher.nullifierHash === nullifierHash;

    component tree = MerkleTreeChecker(levels);
    tree.leaf <== hasher.commitment;
    tree.root <== root;
    for (var i = 0; i < levels; i++) {
        tree.pathElements[i] <== pathElements[i];
        tree.pathIndices[i] <== pathIndices[i];
    }

    // Add hidden signals to make sure that tampering with recipient or fee will invalidate the snark proof
    // Most likely it is not required, but it's better to stay on the safe side and it only takes 2 constraints
    // Squares are used to prevent optimizer from removing those constraints
    signal recipientSquare;
    signal feeSquare;
    signal relayerSquare;
    signal refundSquare;
    recipientSquare <== recipient * recipient;
    feeSquare <== fee * fee;
    relayerSquare <== relayer * relayer;
    refundSquare <== refund * refund;
}`

No output signal. I'm typing for `CommitmentHasher`an instance of `nullifier`to see if it matches. , , , are added to prevent tampering.`secretnullifierHashrecipientrelayerfeerefund`

### `MerkleTreeChecker`template

`// Verifies that merkle proof is correct for given merkle root and a leaf
// pathIndices input is an array of 0/1 selectors telling whether given pathElement is on the left or right side of merkle path
template MerkleTreeChecker(levels) {
    signal input leaf;
    signal input root;
    signal input pathElements[levels];
    signal input pathIndices[levels];

    component selectors[levels];
    component hashers[levels];

    for (var i = 0; i < levels; i++) {
        selectors[i] = DualMux();
        selectors[i].in[0] <== i == 0 ? leaf : hashers[i - 1].hash;
        selectors[i].in[1] <== pathElements[i];
        selectors[i].s <== pathIndices[i];

        hashers[i] = HashLeftRight();
        hashers[i].left <== selectors[i].out[0];
        hashers[i].right <== selectors[i].out[1];
    }

    root === hashers[levels - 1].hash;
}`

### `DualMax`template

`// if s == 0 returns [in[0], in[1]]
// if s == 1 returns [in[1], in[0]]
template DualMux() {
    signal input in[2];
    signal input s;
    signal output out[2];

    s * (1 - s) === 0
    out[0] <== (in[1] - in[0])*s + in[0];
    out[1] <== (in[0] - in[1])*s + in[1];
}`

### `HashLeftRight`template

`// Computes MiMC([left, right])
template HashLeftRight() {
    signal input left;
    signal input right;
    signal output hash;

    component hasher = MiMCSponge(2, 1);
    hasher.ins[0] <== left;
    hasher.ins[1] <== right;
    hasher.k <== 0;
    hash <== hasher.outs[0];
}`

## Circom Lib

### `MiMCSponge`template

In the version specified in torenado-core, the number of rounds was fixed at 220, but now it is possible to specify the number of rounds.

### `Pedersen`template

`template Pedersen(n) {
    signal input in[n];
    signal output out[2];

	// 省略
}`

### `Num2Bits`template

`template Num2Bits(n) {
    signal input in;
    signal output out[n];
    var lc1=0;

    var e2=1;
    for (var i = 0; i<n; i++) {
        out[i] <-- (in >> i) & 1;
        out[i] * (out[i] -1 ) === 0;
        lc1 += out[i] * e2;
        e2 = e2+e2;
    }

    lc1 === in;
}`

## Tornado Cash Classic Trusted Setup Ceremony

I'm running a Trusted Setup Ceremony using Circom 1 and zkUtil.

1. Circuit Compilation

`npx circom circuits/withdraw.circom -o build/circuits/withdraw.json`

`withdraw.circom`Compile with Circom 1 `withdraw.json`and generate

`$ npx circom circuits/withdraw.circom -o build/circuits/withdraw.json
Constraints: 10000
Constraints: 20000
Constraints: 30000
Constraints: 40000
Constraints: 50000`

2. Generate Trusted Setup parameters

`zkutil setup -c build/circuits/withdraw.json -p build/circuits/withdraw.params`

Use zkUtil to generate `withdraw.json`the Trusted Setup parameters for the withdrawal circuit from `withdraw.params`.

`$ zkutil setup -c build/circuits/withdraw.json -p build/circuits/withdraw.params
Loading circuit from build/circuits/withdraw.json...
Generating trusted setup parameters...
Has generated 28300 points
Writing to file...
Saved parameters to build/circuits/withdraw.params`

3. Generate Verification Key

`zkutil export-keys -c build/circuits/withdraw.json -p build/circuits/withdraw.params -r build/circuits/withdraw_proving_key.json -v build/circuits/withdraw_verification_key.json`

Use zkUtil to generate zero-knowledge proof `withdraw_proving_key.json`and verification keys for the withdrawal circuit `withdraw_verification_key.json`.

`$ zkutil export-keys -c build/circuits/withdraw.json -p build/circuits/withdraw.params -r build/circuits/withdraw_proving_key.json -v build/circuits/withdraw_verification_key.json
Exporting build/circuits/withdraw.params...
Created build/circuits/withdraw_proving_key.json and build/circuits/withdraw_verification_key.json.`

4. Generating a verification contract

`zkutil generate-verifier -p build/circuits/withdraw.params -v build/circuits/Verifier.sol`

Use zkUtil to generate a zero-knowledge proof verification contract corresponding to the withdrawal circuit.

`$ zkutil generate-verifier -p build/circuits/withdraw.params -v build/circuits/Verifier.sol
Created build/circuits/Verifier.sol`

`Verifier.sol`The original data can be found at [https://github.com/poma/zkutil/blob/master/src/verifier_groth.sol](https://github-com.translate.goog/poma/zkutil/blob/master/src/verifier_groth.sol?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=es&_x_tr_pto=wapp) .

5. Change the version of the verification contract

`sed -i -e 's/pragma solidity \^0.6.0/pragma solidity 0.5.17/g' ./build/circuits/Verifier.sol`

The Solidity version of the verification contract generated by zkUtil is old, so replace it.

## Governance of Tornado Cash

Until December 2021, you could earn TORN, the governance token, by depositing crypto assets into Tornado Cash pools. This mining is called Anonymity Mining.

Like any other governance system, TORN governs things like changing Tornado Cash protocol parameters and distributing TORN. It operates as a so-called Decentralized Autonomous Organization (DAO).

## Precompiled contracts for zk-SNARK

Ethereum has a pairing precompiled contract for zk-SNARK.

two primesp,qis defined below.

p=21888242871839275222246405745257275088696311157297823662689037894645226208583

q=21888242871839275222246405745257275088548364400416034343698204186575808495617

finite fieldF.pin the setC.1of,

C.1={(X,Y)∈F.p×F.p∣Y2=X3+3}∪{(0,0)}

Define as

(C.1,+)is a group and can define scalar multiplication.

n⋅P.≡(0,0)+P.+･･･+P.⏟n

here,nis a natural number and the pointP.teethC.1is an element of

C.1top point(1,2)ofP.1Define asP.1is generated by(C.1,+)a subgroup ofG.1andG.1is the degreeqis known to be a cyclic group ofG.1point ofP.Againstn⋅P.1=P.The smallest natural number such thatnoflogsP.1⁡(P.)Define aslogsP.1⁡(P.)is at mostq−1is.

body𝟚𝕡F.p2of𝕡F.p[i]/(i2+1)as the setC.2of

C.2={(X,Y)∈F.p2×F.p2∣Y2=X3+3(i+9)−1}∪{(0,0)}

Define as

(C.2,+)and(C.1,+)is a group as well as scalar multiplication can be defined.

C.2top pointP.2is defined below.

P.2≡(11559732032986387107991004021392285783925812861821192530917403151452391805634×i+10857046999023057135944570762232829481370756359578518086990519993285655852781,4082367875863433681332203403145435568316851327593401208105741076214120093531×i+8495653923123431417604973247489272438418190587263600148770280649306958101930)

P.2is generated by(C.2,+)a subgroup ofG.2andG.2teethC.2the only degree aboveqis known to be the cyclic group ofG.2point ofP.Againstn⋅P.2=P.The smallest natural number such thatnoflogsP.2⁡(P.)Define aslogsP.2⁡(P.)is at mostq−1is.

# References

- Introduction to zero-knowledge proofs
- Cryptography and elliptic curves
- Ethereum Yellow Paper
