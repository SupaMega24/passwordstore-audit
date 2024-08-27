### [S-#] Storing password on-chain makes it visable to anyone, regardless of variable view


**Description:** All data stored on-chain is visible to anyone and can be read directly from the blockchain. The `PasswordStore::s_password` variable is intended to be a private variable and only accessed through the `PasswordStore::getPassword` function, which is intended to be only called by the owner of the contract.

We show a method of reading any data off-chain below. 

**Impact:** Anyone can read the private password, severely breaking the functionality of the protocol.

**Proof of Concept:** (Proof of Code)

The test below shows how anyone can read the password on the blockchain. 

**Recommended Mitigation:** 