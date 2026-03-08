# Quick Lib

As part of the Quick tool suite, **Quick Lib** is a structured AWS CDK library that defines reusable constructs, architectural patterns, and infrastructure utilities aimed at standardizing Infrastructure as Code development on AWS.

It serves as a solid technical foundation for building consistent and resilient cloud architectures, incorporating sound practices in design, organization, and use of AWS services. Through composable abstractions and clearly defined patterns, it reduces unnecessary complexity and supports secure, scalable, and maintainable implementations.

---

## 📦 Installation

This package is distributed via GitHub Packages.

```bash
npm install @sosasoftware/quick-lib
```

---

## 🚀 Usage

```ts
import { ExampleConstruct } from "@sosasoftware/quick-lib";

new ExampleConstruct(this, "Example", {
  // props
});
```

---

## ✨ Philosophy

Quick Lib is designed to promote Infrastructure as Code development under clear and sustainable technical standards.

It focuses on:

- **Standardization** — Establishing a coherent foundation for building infrastructure on AWS.
- **Embedded Best Practices** — Integrating architectural criteria directly into reusable constructs and patterns.
- **Structured Reusability** — Avoiding duplication and ad-hoc infrastructure decisions across projects.
- **Clarity and Maintainability** — Prioritizing designs that are understandable, extensible, and aligned with real production environments.

The objective is not to obscure architecture behind excessive abstraction, but to organize it in a consistent and practical manner.

---

## 🏗 Architecture Approach

Quick Lib is organized into three primary layers:

### Constructs
Reusable infrastructure components that encapsulate AWS services and recurring technical decisions.

### Patterns
Compositions of multiple constructs representing cohesive architectural solutions aligned with production best practices.

### Infrastructure Utilities
Supporting abstractions that structure common infrastructure responsibilities while preserving control and transparency.

---

## 🎯 Objectives

- Standardize AWS infrastructure development using CDK.
- Facilitate the implementation of robust cloud architectures.
- Reduce unnecessary complexity in cloud projects.
- Promote scalability, security, and long-term maintainability.
- Provide a reliable foundation for production-grade solutions.

---

## 🛠 Requirements

- Node.js 18+
- AWS CDK v2

---

## ⚠️ Considerations

Quick Lib helps reduce part of the learning curve associated with cloud architecture and AWS CDK, but it does not eliminate it. A foundational understanding of architecture principles, AWS services, and Infrastructure as Code is expected.

Its purpose is to channel that knowledge into a coherent technical framework that supports consistent and sustainable implementation.
