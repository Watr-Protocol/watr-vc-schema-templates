# watr-vc-schema-templates

This repository contains the official Verifiable Credential (VC) schema templates used within the **WATR Protocol** ecosystem. These schemas define the structure, fields, and data types for credentials that can be issued, verified, and consumed by various components of the WATR stack including **WatrID**, **WatrVault**, and ecosystem applications.

## 📘 About WATR Protocol

WATR Protocol is a Layer 1 blockchain subnet built on Avalanche, focused on enabling privacy-preserving, programmable, and identity-aware decentralized finance and trade workflows. This repository supports the **Verifiable Credential (VC)** layer of the WATR identity and data stack.

## 📁 Repository Structure

Each schema template is organized under a separate directory, named after its credential category or use case.

```
schemas/
├── DIDAuth/
│   └── schema.json
├── KYC/
│   └── schema.json
├── TradeLicense/
│   └── schema.json
└── ...
```

Each schema follows the [W3C Verifiable Credentials Data Model](https://www.w3.org/TR/vc-data-model/) and includes:

* `$id`: Unique identifier of the schema
* `@context`: JSON-LD context definitions
* `type`: VC type(s)
* `properties`: Defined attributes
* `required`: Required attributes
* `example`: Optional example data

## ✅ Example

```json
{
  "$id": "https://schemas.watr.org/KYC/v1",
  "@context": [
    "https://www.w3.org/2018/credentials/v1"
  ],
  "type": "KYC",
  "properties": {
    "fullName": {
      "type": "string"
    },
    "nationalID": {
      "type": "string"
    },
    "country": {
      "type": "string"
    }
  },
  "required": ["fullName", "nationalID", "country"]
}
```

## 🔧 Usage

1. **Referencing in VCs**
   Each schema can be referenced by its `$id` during VC issuance using WatrID SDKs or Issuer Services.

2. **Validation**
   Applications can validate credential structure against the schema using standard JSON Schema validation libraries.

3. **Versioning**
   Schemas are versioned via folder naming (e.g., `v1`, `v2`) for backward compatibility and traceability.

## 🚀 Contributing

We welcome contributions from the community to extend or improve schema definitions.

### To contribute:

1. Fork the repository
2. Create a new branch: `git checkout -b feature/schema-name`
3. Add or update your schema in the appropriate folder
4. Commit your changes
5. Submit a pull request

### Contribution Guidelines

* Use lowerCamelCase for field names
* Ensure `required` fields are minimal but essential
* Include example data when possible
* Avoid personally identifiable data in examples

## 📜 License

This repository is licensed under the [MIT License](LICENSE).

## 🌐 Links

* [WATR Protocol](https://watr.org)
* [WatrID Documentation](https://docs.watr.org/watrid)
* [Verifiable Credentials Specification](https://www.w3.org/TR/vc-data-model/)
