# Decentralized Identifiers (DID) : DID-AVVCYBER for TIFAC-CORE in Cyber Security, Amrita Vishwa Vidyapeetham, Coimbatore

### DID Format
The format of the did is shown below

```
did:avvcyber:<network-id>:<avvcyber-specific-id>
<network-id>: btc / eth-main / eth-ropsten / bnb / iota
<avvcyber-specific-id>: version + keccak256(keccak256(<Base DID Document>))
```

### DID Specification Document

The DID Specification Document Example for the Ethereum-Ropsten Network is given.
```
 {
    "@context": [
      "https://www.w3.org/ns/did/v1",
      "https://w3id.org/security/suites/ed25519-2020/v1",
      "https://amrita-tifac-cyber-blockchain.github.io/DID-AVVCYBER/did-avvcyber-v1"
    ],
    "id": "did:avvcyber:eth-ropsten",
    "created": "2022-01-01T00:00:00Z",
    "updated": "2022-01-01T00:00:00Z",
    "authentication": [
      {
        "id": "did:avvcyber:eth-ropsten",
        "type": "Ed25519VerificationKey2018", 
        "controller": "did:avvcyber:eth-ropsten",
        "publicKeyMultibase": ""
      }
    ],
    "capabilityInvocation": [
      {
        "id": "did:avvcyber:eth-ropsten",
        "type": "Ed25519VerificationKey2018", 
        "controller": "did:avvcyber:eth-ropsten",
        "publicKeyMultibase": ""
      }
    ],
    "capabilityDelegation": [
      {
        "id": "did:avvcyber:eth-ropsten",
        "type": "Ed25519VerificationKey2018", 
        "controller": "did:avvcyber:eth-ropsten",
        "publicKeyMultibase": ""
      }
    ],
    "assertionMethod": [
      {
        "id": "did:avvcyber:eth-ropsten",
        "type": "Ed25519VerificationKey2018", 
        "controller": "did:avvcyber:eth-ropsten",
        "publicKeyMultibase": ""
      }
    ]
}
```

### Verifiable Credentials

```
{  
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://w3id.org/citizenship/v1",
    "https://amrita-tifac-cyber-blockchain.github.io/DID-AVVCYBER/did-avvcyber-v1"
  ],
  "type": [
    "VerifiableCredential",
    "CollegeID"
  ],
  "credentialSubject": {
    "id": "did:avvcyber:eth-ropsten",
    "type": [
      "CollegeID",
      "Person"
    ],
    "givenName": "RAMAGURU",
    "familyName": "RADHAKRISHNAN",
    "gender": "Male",
    "image": "data:image/png;base64,iVBORw0KGgoA....AAAElFTkSuQmCC",
    "Date-of-Reg": "2017-07-11",
    "Dept": "CYS",
    "Category": "GATE",
    "birthCountry": "India",
    "birthDate": "1990-02-24"
  },
  "issuer": "did:avvcyber:eth-ropsten",
  "issuanceDate": "2017-07-11T05:10:44Z",
  "identifier": "17018",
  "name": "College Identity",
  "description": "Amrita School of Engineering, Coimbatore",
  "proof": {
    "type": "Ed25519Signature2018",
    "created": "2017-07-11T05:10:44Z",
    "proofPurpose": "assertionMethod",
    "verificationMethod": "did:avvcyber:eth-ropsten"
  }
}
```

### DID Interface
The below smart contract interface allows multiple stakeholders to create and manage their DIDs.

```
interface avvcyberDID {
    function createDID(string id, bytes32 hash, string uri) public returns (string);
    function deleteDID(string did) public;
    function updateHash(string did, bytes32 hash) public;
    function updateURI(string did, string uri) public;
    function getHash(string did) public view returns (bytes32);
    function getURI(string did) public view returns (string);
}
```

### Citeas
Ramaguru R. Decentralized Identifier (DID) - DID:AVVCYBER - Specification (V1). (2022). TIFAC-CORE in Cyber Security, Amrita Vishwa Vidyapeetham, Coimbatore. Available in [Identity Decentralized](https://decentralized-id.com/web-standards/w3c/decentralized-identifier/did-methods/)
