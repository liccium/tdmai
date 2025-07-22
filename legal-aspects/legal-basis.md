# Legal Basis

## Disclaimer on Legal Applicability

This vocabulary is designed to provide a standardised, machine-readable means for rightsholders to communicate usage preferences concerning the use of protected content for automated processing or text and data mining (TDM), artificial intelligence (AI) training, generative AI training, RAG/inference, and search, involving AI.

This vocabulary operates in the context of ongoing legal debate regarding the scope and applicability of statutory TDM exceptions – particularly whether such exceptions, as provided for in EU and national copyright laws, extend to the training of generative AI systems. Current academic and legal discourse, including the work of Dornis and Stober (2024), indicates divergent interpretations and unresolved questions in this area (Dornis, T.W. & Stober, S. (2024). Urheberrecht und Training generativer KI-Modelle – Technologische und juristische Grundlagen, Recht und Digitalisierung, Nomos Verlag.[ Open Access version](https://www.nomos-elibrary.de/10.5771/9783748949558/urheberrecht-und-training-generativer-ki-modelle?page=1); also available at SSRN:[ https://ssrn.com/abstract=4946214](https://ssrn.com/abstract=4946214)). Currently, the debate focuses on the evolving interpretation of Article 4(3) of Directive (EU) 2019/790 (CDSM Directive) and the interpretation of obligations in Article 53(1)(c) AI Act. Similar uncertainty exists in U.S. law, as evidenced in ongoing federal litigation such as Bartz v. Anthropic, where courts declined early dismissal of copyright claims involving AI training data.

The inclusion of terms and categories in this vocabulary does not constitute a legal determination of whether any given use is permitted or prohibited under applicable law. Rather, it reflects the intention of rightsholders to express usage rights, e.g. reserve rights, to the fullest extent permitted by law and to provide clear signals to users and AI developers in light of legal uncertainty.

Implementers and users of this vocabulary are advised to seek legal counsel regarding the specific application of copyright exceptions and limitations in their jurisdiction. The use of this vocabulary does not substitute for legal advice nor does it imply endorsement of any particular legal interpretation. The use of this vocabulary cannot substitute for formal legal consultation or override court interpretations or authoritative legal standards.

## The EU Copyright Directive

[Article 4 of the EU Copyright Directive 2019/790 (DSM Directive)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32019L0790) requires EU Member States to provide an "exception \[...] of this Directive for reproductions and extractions of lawfully accessible works and other subject matter for the purposes of text and data mining", which is defined as "any automated analytical technique aimed at analysing text and data in digital form in order to generate information which includes but is not limited to patterns, trends and correlations".

The DSM Directive distinguishes between TDM for scientific purposes and for other purposes. Article 3 provides a provision for scientific purposes, while Article 4 regulates all other purposes. Although Article 4 does not explicitly mention any specific, non-scientific purposes of TDM, it is assumed that acts of training models of AI include acts of TDM as an essential element.&#x20;

The applicability of Article 4 CDSM to AI training is referenced in Article 53(1)(c) of the AI Act, which obliges providers to respect copyright and opt-out declarations. While this interpretation is operationalised under the AI Act, the European Parliament has called for clearer legal provisions or a dedicated exception to regulate generative AI training (Motion for a European Parliament Resolution on Copyright and generative artificial intelligence – opportunities and challenges, p. 12 (2025/2058(INI)), published June 26, 2025, [https://www.europarl.europa.eu/doceo/document/JURI-PR-775433\_EN.pdf](https://www.europarl.europa.eu/doceo/document/JURI-PR-775433_EN.pdf))

Article 4 (3) CDSM further elaborates that "the exception or limitation provided for in paragraph shall apply on condition that the use of works and other subject matter referred to in that paragraph has not been expressly reserved by their rightholders in an appropriate manner, such as machine-readable means in the case of content made publicly available online."&#x20;

## International Applicability of the Relevant Provisions within the EU Copyright Directive and the AI Act

The AI Act and the obligation to respect TDM opt-out declarations raise complex questions about their territorial applicability on cross-border uses. If, for instance, an AI provider in the US trains an AI model, using servers and content available in the US, it is questionable whether this provider must respect TDM opt-out declarations. However, Recital 106 of the AI Act expresses the principle that no provider shall gain a competitive advantage by applying lower copyright standards outside the EU. The AI Act assumes that the provider must respect the declaration at least when marketing these models on the European Union Market, in order “to ensure a level playing field among providers of general-purpose AI models where no provider should be able to gain a competitive advantage in the Union market by applying lower copyright standards than those provided in the Union.” (Recital 106 of the European AI Act). Even if this assumption is only part of a (non-binding) recital, it expresses the general objective of the Act, confirmed by obligations affecting providers irrespective of their seat such as those contained in § 53 of the AI Act.

Traditionally, copyright laws are territorial in the sense that reproductions during AI model training are governed by the copyright laws of the country where the training occurs, this would primarily suggest the applicability of US law to the case. The EU Copyright Directive, including its opt-out provision for text and data mining (TDM), is European Union (EU) legislation. As such, it primarily applies to EU member states and the acts of using copyrighted works on EU territory.

However, the scope of the AI Act, referring to the copyright provisions of the EU Copyright Directive goes beyond this regulation. The AI Act imposes very specific compliance duties, namely, “through state-of the art technologies” to comply with opt-out declaration (Art. 53 (1) lit. c) AI Act), on any provider placing general-purpose AI models on the EU market, regardless of their location including the obligation to implement a copyright policy and state-of-the-art technologies to comply with opt-outs (Code of Practice, Copyright Chapter). This means even if the AI training occurs outside the EU, such model must comply with the AI Act when the model or an application based thereon is offered on the European Union market. The Act's goal is to ensure fair competition and protect individual rights within the territorial scope of EU law. Therefore, if an AI model is not developed according to the AI Act, it cannot be offered in the EU, regardless of whether the content used for training has been created by a rightsholder based in the EU or on US territory.

Alternatively, _Rosati_ and other legal scholars suggest that the application of the AI Act could depend on the localization of another act of use, namely, on whether the AI provider has crawled data from websites hosted in the EU. _Rosati_ also suggests that “terms of service of AI model providers that seek to remove any liability potentially arising from the use of their models might turn out to be ineffective towards third-party rightholders or users of their services.” This approach is consistent with the specific requirements of the AI Act, such as automatic crawling and the obligation to comply with machine-readable rights reservations. This solution emphasizes that if content is hosted in the EU, AI providers accessing this content by way of crawling during or as a part of AI training processes should comply with applicable rules in the EU, even if the subsequent training takes place elsewhere.

In summary, while traditional copyright principles may in effect limit territorial applicability, the AI Act seeks to ensure compliance with EU standards for AI models offered within the EU, potentially extending its reach beyond traditional territorial boundaries.

## Applicability to Rightsholders based outside the European Union

Rightsholders from the US or from other countries outside the EU may benefit from the EU Copyright Directives if their content is used within the EU. The Parliament has also proposed establishing a central EUIPO registry of opt-outs, which could support international rightsholders in signaling their preferences effectively. (JURI Report, paras 6–9 and Explanatory Statement; [https://www.europarl.europa.eu/doceo/document/JURI-PR-775433\_EN.pdf](https://www.europarl.europa.eu/doceo/document/JURI-PR-775433_EN.pdf)).

If the content of US rightsholder is affected by uses happening on EU territory and is lawfully accessible within the EU, AI companies are marketing their products in the EU and EU-based users are using it, these AI companies must comply with the EU Copyright Directive. Notably, U.S. courts have begun scrutinising whether AI providers owe a duty to respect copyright when using publicly accessible content for training, as in Bartz v. Anthropic.

Therefore, US and other third country rightsholders may want to consider the instruments provided for their protection by the EU Copyright Directive if they want to control the use of their content within the EU. They can implement the opt-out provision to prevent their content from being used for TDM by AI providers marketing their products in the EU.

## Implementation Considerations for Machine-Readable Opt-Out

US and other third country rightsholders can use machine-readable means, such as the International Standard Content Code (ISCC) or other EU standardized formats as discussed in the Code of Practice (AI Code of Practice, Copyright Chapter, Measure 1.3), to identify their works and bind opt-out reservations that express in an automated way that their works should not be used for TDM. This would help ensure that EU-based entities can respect their opt-out.

Practical Steps – US and other third country rightsholders should:

1. Assess if their content is accessible within the EU.
2. Implement a machine-readable opt-out if they wish to prevent TDM through content that is accessible and marketed within the EU.
3. Monitor compliance and take necessary actions if their opt-out is not respected.
4. Monitor relevant litigation (e.g. Bartz v. Anthropic) in the U.S. and other jurisdictions to track how courts assess copyright liability in AI training contexts.

In summary, the EU Copyright Directive's opt-out provision can be applicable if an AI model or the AI application is marketed within the European Union. Implementing a machine-readable opt-out, using the ISCC as an identifier that can help to point to rights and opt-out reservations, can provide an effective and enforceable instrument to US and other third country rightsholders to manage their content's use.

## Sources

Rosati E. Infringing AI: Liability for AI-Generated Outputs under International, EU, and UK Copyright Law. European Journal of Risk Regulation. 2025;16(2):603-627. doi:10.1017/err.2024.72  Rendas/Hartmann; From Brussels to Brasília: How the EU AI Act Could Inspire Brazil’s Generative AI Copyright Policy; GRUR Int. 2024, p. 495.

HiQ Labs, Inc. v LinkedIn Corp. 31 F.4th 1180, 1187 n. 3 (9th Cir. 2022).

See Bartz v. Anthropic PBC, No. 3:24-cv-00518, Dkt. 231 (N.D. Cal. May 6, 2024), where the court denied Anthropic’s motion to dismiss copyright claims stemming from the alleged ingestion of protected content into AI models, citing unresolved factual and legal questions concerning fair use.

\
