---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Opt-out, opt-in and content licensing

TDM·AI defines a vocabulary and technical specification for public, machine-readable opt-outs from text and data mining (TDM) and AI training. It is not designed to facilitate active opt-ins or serve as a licensing mechanism. This is by design, and for good reason.

### Opt-Out Is Not Licensing

Opt-out declarations, as supported by TDM·AI, are statements of reservation — not offers of permission. They are meant to communicate, in a standardised and interoperable way, that certain rights are not granted for specific AI-related uses of content. This applies broadly, including to unknown or future actors. It’s a public signal, not a bilateral agreement.

By contrast, licensing and opt-in mechanisms are contractual, negotiated, and typically confidential. A content license — whether exclusive or non-exclusive — is a transaction between identified parties. These transactions often involve terms and conditions that vary widely and are not publicly disclosed. For example, a publisher may license a dataset to one model developer under specific restrictions while denying access to others.

Because of their private, individualised nature, such agreements do not require a public vocabulary or machine-readable format. In practice, content licensing functions through legal contracts, not declarations or protocols.

### Different Purposes, Different Infrastructures

* Opt-out declarations serve a preventive purpose: They are meant to stop unauthorised or undesired use of content by signaling a refusal of permission under relevant exceptions (e.g., the DSM TDM exception).
* Opt-in agreements, on the other hand, are permissive and context-specific: They are about granting access under agreed terms.

TDM·AI provides the infrastructure for the former – not the latter.

### Exceptions vs. Licenses

TDM·AI is built around the EU legal framework, particularly the TDM exception in Article 4 of the Copyright in the Digital Single Market (CDSM) Directive. Under this framework:

* By default, AI model developers may use copyrighted works for TDM unless a rightsholder explicitly opts out.
* An opt-out overrides the exception, restoring the need for explicit permission.

This is different from licensing, which would apply regardless of the exception. Opt-outs do not grant rights; they reserve them.

In this context, TDM·AI allows rightsholders to signal their refusal of permission in a way that is compatible with EU law – and interoperable across the internet. Licensing, being a separate legal process, falls outside the scope of this technical standard.

### Complementary, Not Redundant

A rightsholder may declare an opt-out using TDM·AI while still entering into licensing deals with specific parties. This is not a contradiction. In fact, it is expected:

* The opt-out sets a default position: no permission granted.
* A license creates an exception to that default: permission granted under specified terms.

TDM·AI makes no assumptions about licensing and does not interfere with it. It provides the public, standardised layer for opt-out declarations — nothing more, nothing less.

\
