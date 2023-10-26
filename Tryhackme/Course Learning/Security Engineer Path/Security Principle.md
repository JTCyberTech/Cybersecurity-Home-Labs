# CIA

<h2></h2>

# DAD

<h2></h2>

# Fundamental Concepts of Security Models

Three Fundamental Concept of Security Models

- Bell-LaPadula Model
- Biba Integrity Model
- Clark Wilson Model

<h2></h2>

Bell-LaPadula Model

- Aims to achieve "Confidentiality" with 3 rules:

  - Simple Security Property: Referred as `"no read up"`. Subject with `lower security` level `cannot read` to object at a `higher security level`. Prevent access to sensitive information above authorized level.
 
  - Star Security Property: Referred as `"no write down"`. Subject at `higher security` level `cannot write` to object at a `lower security level`. Prevent the disclosure of sensitive information to subject of lower security level.
 
  - Discretionary-Security Property: Uses access `Matrix` to allow read and write operations. Example: 
