# Bachelor Thesis

**Title:** Zero-Knowledge Proof Based Authentication for Microservices

This repository contains the materials for my Bachelor's thesis: the manuscript, figures/diagrams, and the defense presentation. The thesis designs and implements a Rust library for authenticating service-to-service HTTP requests with non-interactive Schnorr proofs (Zero-Knowledge Proofs), and demonstrates it inside a small microservice application.

The library and demo application themselves live in separate repositories:

- [zkp-auth-lib](https://github.com/natasakasikovic/zkp-auth-lib) — the `schnorr` and `auth` crates (proof generation/verification, HTTP request binding, replay protection)
- [zkp-auth-demo](https://github.com/natasakasikovic/zkp-auth-demo) — `order-service`, `warehouse-service` and `payment-service`, authenticating their internal calls with the library

## Contents

| File / folder | Description |
|---|---|
| `thesis.docx` / `thesis.pdf` | Full thesis manuscript |
| `presentation.pptx` | Defense presentation |
| `diagrams/` | Architecture and flow diagrams (library architecture, demo application architecture, order flow) |
| `images/` | ZKP protocol illustrations (interactive vs. non-interactive) used in the theoretical chapter |

## Thesis structure

1. **Увод** — motivation: authenticating microservices without exchanging static secrets
2. **Теоријске основе Zero-Knowledge Proof протокола** — completeness/soundness/zero-knowledge, interactive vs. non-interactive ZKP, the Schnorr protocol, ZKP applications, and traditional service-authentication approaches (API keys, JWT, mTLS) with their security risks
3. **Пројектовање и имплементација ZKP библиотеке** — library architecture (`schnorr` + `auth` crates), key generation, proof generation/verification, binding a proof to its HTTP request context, replay protection, and testing
4. **Примjeна библиотеке у микросервисном окружењу** — the demo application (OrderService, WarehouseService, PaymentService), integrating the library into internal service calls, and measured ZKP authentication performance compared against representative operations from the traditional approaches
5. **Закључак**, **Литература**, **Биографија**
