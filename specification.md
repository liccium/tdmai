# Specification

## Specification

1. **Declarations**:
   * **Opt-Out**: A machine-readable declaration by the rightsholder prohibiting use of content for AI training.
   * **Permission**: A machine-readable declaration indicating the rightsholder's consent for TDM for AI, or their change of stance from a previous restriction.
2. **ISCC Integration**:
   * Utilise ISCC as a decentralised identifier for content.
   * ISCC remains effective even with content alterations, metadata loss, or when taken out of context.
3. **Creator Credentials**:
   * Ensure proper and verifiable attribution of rights, permissions, and restrictions.
   * Publicly accessible and immutable credentials with timestamping for verifiability.
   * Allow for self-sovereign control, portability, and interoperability of credentials.
4. **Timestamp**:
   * Every declaration should be timestamped to provide clear information about when it was issued.
5. **Machine-Readable Declarations**:
   * JSON format indicating the TDM·AI stance (`true` for permission, `false` for opt-out) along with a summary and detailed policy description.
6. **Content Links**:
   * Metadata files provided for each declaration, ensuring federated access and storage.
