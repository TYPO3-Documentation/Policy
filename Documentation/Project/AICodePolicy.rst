:navigation-title: Policy on AI-Assisted Code
..  include:: /Includes.rst.txt
..  _ai-assisted-code:

==========================================================
Policy on AI-Assisted Code in TYPO3 Open Source Extensions
==========================================================

:Document Owner: TYPO3 Association Board
:Authors: TODO; populate once approved
:Version: Draft, 20 July 2026


..  contents::
    :local:
    :depth: 1


1. Purpose and Scope
====================

The rapid adoption of AI-assisted development tools across the software industry requires the TYPO3 ecosystem to establish clear, pragmatic guidelines for contributions to TYPO3 open source extensions. This policy aims to balance innovation and developer productivity with quality assurance, legal clarity, and community trust.

This policy applies to all contributions to extensions published in the TYPO3 Extension Repository (TER) and on official TYPO3 GitHub repositories. It covers code, documentation, and configuration that has been generated, co-developed, or substantially influenced by AI coding assistants, large language models (LLMs), or similar generative AI tools.

The policy is deliberately pragmatic. *It neither prohibits nor stigmatizes AI-assisted development*. Instead, it establishes a framework of transparency, accountability, and quality assurance that allows the TYPO3 community to integrate AI tools responsibly while protecting the legal and technical integrity of the ecosystem.

2. Motivation
=============

AI-assisted development tools are now a routine part of how software is written, and TYPO3 extension development is no exception. Contributors increasingly rely on AI coding assistants, large language models, and similar generative tools to accelerate their work, explore unfamiliar APIs, and draft boilerplate code.

This shift creates both opportunity and risk for an open source ecosystem built on trust, code quality, and legal clarity. Left unaddressed, it leaves contributors and reviewers without answers to basic questions: whether and how AI involvement should be disclosed, whether AI-generated code carries different quality or security risks than human-written code, and who bears responsibility when an AI-assisted contribution introduces a defect or a legal complication.

This policy exists to answer those questions with a stable, principle-based framework, so that contributors, maintainers, and reviewers can make consistent decisions as AI tools continue to evolve. A survey of how other open source projects have approached this same challenge is provided in `Appendix C`_ for reference.

3. Core Principles
==================

3.1 Human Responsibility Remains Indivisible
--------------------------------------------

Every contributor who submits code to a TYPO3 extension bears full responsibility for the quality, security, functionality, and license compliance of their contribution, regardless of how the code was produced. AI is a tool, not an author. The contributor is accountable for understanding, reviewing, and standing behind every line they submit, just as they would be for code adapted from Stack Overflow, documentation examples, or any other source.

This principle is non-negotiable and forms the foundation of the entire policy. It is consistent with standard TYPO3 contribution practice, under which contributors publish their code under the extension's license and remain personally accountable for it; TYPO3 does not require a separate Contributor License Agreement, and this policy does not introduce one. It ensures that the established chain of accountability remains intact.

3.2 Transparency Through Disclosure
-----------------------------------

Contributors are expected to disclose when a contribution has been substantially generated or co-developed using AI tools. This disclosure serves the community in several important ways: it provides valuable context for code reviewers, it builds a shared understanding of how AI tools perform in the TYPO3 ecosystem, and it creates an audit trail should legal questions arise in the future.

Disclosure is required when AI tools have generated the structural logic or substantial portions of the contributed code. It is not required for incidental use such as IDE autocompletion, syntax suggestions, code formatting, or using AI to understand existing code.

The recommended disclosure mechanism is a tag in the commit message or pull request description: ``AI-assisted: [tool name]`` (e.g., ``AI-assisted: Claude claude-opus-4-20250514`` or ``AI-assisted: GitHub Copilot``). This follows the pattern established by the Linux kernel community and is intentionally lightweight.

3.3 Quality Standards Apply Uniformly
-------------------------------------

AI-generated code must meet the same quality standards as any other contribution to the TYPO3 ecosystem. There is no reduced bar, but there is also no elevated bar. Specifically, all contributions must comply with the TYPO3 Coding Guidelines, pass existing CI/CD checks including PHPStan, PHPCS, and unit tests, follow PSR standards, include appropriate documentation, and be compatible with the declared TYPO3 version support.

3.4 Security-Conscious Development
----------------------------------

Contributors using AI tools must exercise particular vigilance with security-sensitive code. AI models can generate plausible-looking code that contains subtle security vulnerabilities, including SQL injection patterns, insecure authentication flows, inadequate input validation, or improper use of TYPO3's security APIs. Contributors must demonstrate that they understand and have reviewed any security-relevant code they submit, regardless of its origin.

Extension reviewers should pay special attention to security patterns in contributions flagged as AI-assisted, not because AI-generated code is inherently less secure, but because the patterns of insecurity differ from typical human-introduced vulnerabilities.

3.5 License and Intellectual Property Clarity
---------------------------------------------

By submitting a contribution, the contributor affirms that the code may be published under the extension's license (typically GPL-2.0-or-later) and that no third-party rights are infringed. This affirmation applies equally to AI-assisted and human-authored code.

Our `current stance on the license compatibility of AI-generated code <https://news.typo3.com/article/typo3-association-board-meeting-protocol-8-july-2026/board-statement-on-gpl-and-ai-code>`__ is that compatibility with the GPL depends on the *provenance* of a contribution, not on the tool used to produce it. AI-generated code is not inherently incompatible with GPL-2.0-or-later. What matters is whether the contribution can lawfully be published under the extension's license without reproducing third-party material under incompatible terms. Responsibility for ensuring this rests with the contributor who submits the code.

Contributors should be aware that the copyright status of AI-generated code remains legally unsettled in many jurisdictions. By submitting AI-assisted code, the contributor accepts responsibility for any intellectual property claims that may arise and warrants, to the best of their knowledge, that the contribution does not reproduce copyrighted material from other sources.

3.6 Provenance Certification via DCO Sign-off
---------------------------------------------

To make the affirmation in Section 3.5 explicit and auditable, contributions should carry a Developer Certificate of Origin (DCO) sign-off. Following the TYPO3 Association Board's July 2026 statement, this is the recommended mechanism for certifying provenance: a lightweight, transparent alternative to a full Contributor License Agreement, which TYPO3 deliberately does not require.

The DCO sign-off is a deliberate ``Signed-off-by:`` trailer line in the commit message, distinct from Git's author field. By adding it, the contributor certifies the terms of the `Developer Certificate of Origin <https://developercertificate.org/>`__: that they have the right to submit the contribution under the extension's open source license. This representation applies with equal force whether or not AI tools assisted in producing the code, and it does not shift responsibility onto those tools. Because it is recorded in the commit history, the sign-off makes the contributor's provenance representation explicit and auditable, which is particularly valuable for detecting the unintentional inclusion of third-party material.

The DCO sign-off is separate from, and complementary to, the ``AI-assisted:`` disclosure tag described in Section 3.2. The sign-off certifies provenance and remains a human act; the disclosure tag names any AI tools involved. Both may appear in the same commit.

4. Practical Implementation
===========================

4.1 For Contributors
--------------------

When using AI tools to develop TYPO3 extension code, contributors should follow these practices:

1. Review all AI-generated code line by line before committing. Ensure you understand what every part of the code does and why.
2. Verify that AI-generated code uses current, valid TYPO3 Core APIs. AI models frequently suggest deprecated methods, non-existent classes, or outdated patterns. Always check against the official TYPO3 API documentation for the target version.
3. Run the full test suite and static analysis before submitting. AI-generated code may pass cursory inspection but fail under PHPStan or functional tests.
4. Add the AI-assisted tag to your commit message or pull request when the tool has generated structural code. You do not need to tag commits where AI was used only for autocompletion, formatting, or understanding existing code.
5. Never submit AI output without testing it in a running TYPO3 environment. Code that compiles or passes static analysis may still fail at runtime due to incorrect assumptions about the TYPO3 framework.
6. Pay special attention to edge cases, error handling, and TYPO3-specific conventions such as TCA configuration, Extbase patterns, and Fluid template integration. These are areas where AI tools most commonly produce subtly incorrect output.
7. Sign off your commits with a ``Signed-off-by:`` trailer to certify the Developer Certificate of Origin (see Section 3.6). Most Git workflows add this automatically with ``git commit -s``. The sign-off certifies that you have the right to submit the code under the extension's license, and remains your representation regardless of whether AI tools were involved.

4.2 For Extension Reviewers and Maintainers
-------------------------------------------

Reviewers should treat AI-assisted contributions with the same rigor as any other contribution. Additional attention is warranted in specific areas:

1. API validity: Verify that referenced TYPO3 classes, methods, and constants actually exist in the target TYPO3 version. AI tools trained on mixed-version documentation frequently hallucinate plausible but non-existent API calls.
2. Security patterns: Check for common AI-generated security anti-patterns, including raw SQL queries instead of QueryBuilder, missing CSRF protection, direct use of $_GET/$_POST instead of TYPO3 request handling, and hardcoded credentials or tokens.
3. Architectural coherence: AI-generated code sometimes produces technically correct but architecturally inconsistent results. Ensure contributions align with the extension’s existing patterns and the broader TYPO3 architectural principles.
4. Test coverage: Verify that contributed tests actually exercise the relevant code paths and are not superficial AI-generated tests that pass without meaningful assertions.

4.3 For Extension Owners
------------------------

Extension owners who publish on TER or maintain repositories on GitHub are encouraged to include a section in their “CONTRIBUTING.md” file that addresses AI-assisted development. This section should state whether the extension follows this TYPO3 Association policy, specify any additional requirements or preferences, and provide project-specific guidance for AI tools, such as an “AGENTS.md” file with relevant coding conventions and architectural decisions.

Extension owners may adopt stricter policies than this baseline, for example requiring that all AI-assisted commits be reviewed by a second human contributor, or prohibiting AI-generated code in specific subsystems. Such project-level policies take precedence over this general guidance.

5. What This Policy Deliberately Does Not Do
============================================

This policy does not prohibit or stigmatize AI-assisted development. The boundary between AI-assisted and non-AI-assisted code is increasingly blurred as AI capabilities are embedded into IDEs, compilers, and development workflows. A binary distinction would be both artificial and counterproductive.

This policy does not prescribe or exclude specific AI tools. Tool landscapes evolve rapidly, and any list of approved or banned tools would be outdated within months. The focus is on outcomes, meaning code quality, security, and license compliance, not on the specific tools used to achieve them.

This policy does not attempt to resolve the international legal debate about copyright and AI-generated code. Instead, it places the burden of compliance on the individual contributor, which mirrors standard open source practice for code from any source.

This policy does not create a separate review track for AI-assisted contributions. All code goes through the same review process. The disclosure tag provides context but does not trigger a different workflow.

6. Disclosure Guidelines: When and How
======================================

6.1 Disclosure Is Expected When:
--------------------------------

- An AI tool generated the core logic or structure of a function, class, or module.
- An AI tool produced a substantial portion (roughly more than 50 %) of the lines in a commit.
- An AI tool was used to generate TCA configuration, database schemas, or other structural elements.
- An AI agent autonomously created a pull request or series of commits.

6.2 Disclosure Is Not Expected When:
------------------------------------

- An IDE’s built-in AI features provided autocompletion or syntax suggestions.
- An AI tool was used to understand or explain existing code.
- An AI tool assisted with formatting, linting fixes, or mechanical refactoring.
- An AI tool was used to draft commit messages, documentation, or comments that were then reviewed and edited.

6.3 Format
----------

In commit messages, add a trailer line: `AI-assisted: [tool identifier]`

In pull request descriptions, include a note such as: *"This PR includes code generated with the assistance of [tool name]. All code has been reviewed and tested by the submitting contributor."*

The disclosure does not need to include the specific prompts used, the number of iterations, or other process details. The purpose is to signal provenance, not to document the development process exhaustively.

7. Governance and Evolution
===========================

This policy is a living document. The legal, technical, and cultural landscape around AI-assisted development is evolving rapidly, and the policy must evolve with it. The TYPO3 Association commits to reviewing this policy at least annually, or more frequently if significant developments warrant it.

The following mechanisms support ongoing governance:

- **Annual review:** The TYPO3 Association Board will review and, if necessary, update this policy at least once per year, incorporating feedback from the community, legal developments, and practical experience.
- **Community feedback:** An open feedback channel will be maintained for contributors, reviewers, and extension owners to share experiences and suggest improvements to this policy.
- **Legal monitoring:** The TYPO3 Association will monitor legal developments regarding AI-generated code and copyright, particularly in EU jurisdictions relevant to the TYPO3 community, and update the policy as needed.
- **Tooling evolution:** As new disclosure and provenance mechanisms emerge (such as the proposed SPDX AI-generated code identifiers), the TYPO3 community will evaluate their adoption.

8. Relationship to Existing Frameworks
======================================

This policy supplements, but does not replace, the following existing TYPO3 governance documents:

- `TYPO3 Coding Guidelines <https://docs.typo3.org/m/typo3/reference-coreapi/main/en-us/CodingGuidelines/Index.html>`__`: All quality and style requirements remain fully in effect.
- `Developer Certificate of Origin (DCO) <https://developercertificate.org/>`__: This policy introduces a DCO sign-off (Section 3.6) as the recommended way to certify the provenance and license grant for contributions, regardless of how they were produced. It is proposed as a lightweight alternative to a separate Contributor License Agreement, which TYPO3 does not require.
- TYPO3 Extension Review Guidelines: The existing review process and criteria remain the primary quality gate.
- TYPO3 Security Policy: All security reporting and handling procedures remain unchanged.
Where a project-level “CONTRIBUTING.md” contains AI-specific provisions that are stricter than this policy, the project-level provisions take precedence.

.. _Appendix A:

Appendix A: Suggested “CONTRIBUTING.md” Section
===============================================

Extension maintainers may adapt the following text for inclusion in their project’s “CONTRIBUTING.md”:

.. code-block:: markdown

    ## AI-Assisted Contributions

    We accept contributions that use AI coding assistants.
    This project follows the TYPO3 Association Policy on
    AI-Assisted Code. Please note:

    - You are fully responsible for all code you submit.
    - Sign off your commits (`git commit -s`) to certify the
      Developer Certificate of Origin. This applies whether or
      not AI tools were involved.
    - Please tag AI-assisted commits with:
      `AI-assisted: [tool name]`
    - Verify all code against current TYPO3 APIs.
    - Run linters, analyzers and tests before submitting.
    - Review security-sensitive code with extra care.

Appendix B: Suggested Commit Message Format
===========================================

The following examples illustrate the expected disclosure format:

.. code-block:: text
    Example 1: Feature development

    [FEATURE] Add Solr vector search support

    Implements dense vector indexing and kNN query
    support for Apache Solr integration.

    AI-assisted: Claude Code (claude-opus-4)
    Signed-off-by: Developer Name <dev@example.com>

.. code-block:: text
    Example 2: Bug fix

    [BUGFIX] Fix SQL injection in search query builder

    Replaces direct string concatenation with
    QueryBuilder parameter binding.

    AI-assisted: GitHub Copilot
    Signed-off-by: Developer Name <dev@example.com>

.. _Appendix C:

Appendix C: Landscape Analysis and Research Notes
=================================================

Before defining a TYPO3-specific approach, it is instructive to examine how other major open source projects have addressed this challenge. The spectrum ranges from outright prohibition to open acceptance, with most mature projects settling somewhere in between. This analysis reflects the state of AI code policies across major open source projects as of February 2026.

+---------------------+---------------------------+-----------------------------------------------+---------------------------------+
| Project             | Stance                    | Key Provisions                                | Approach                        |
+---------------------+---------------------------+-----------------------------------------------+---------------------------------+
| `Linux Kernel`_     | Permitted with disclosure | Assisted-by tag naming the AI agent and       | Pragmatic, transparency-focused |
|                     |                           | exact model version; Signed-off-by /          |                                 |
|                     |                           | DCO certification remains human-only          |                                 |
+---------------------+---------------------------+-----------------------------------------------+---------------------------------+
| `QEMU`_             | Prohibited                | Full ban based on DCO interpretation          | Strict, legally conservative    |
|                     |                           | requiring human authorship; legal risk        |                                 |
|                     |                           | considered too high                           |                                 |
+---------------------+---------------------------+-----------------------------------------------+---------------------------------+
| `Gentoo Linux`_     | Prohibited                | Unanimous council vote banning all            | Strict, values-driven           |
|                     |                           | AI/ML-generated contributions on copyright,   |                                 |
|                     |                           | quality, and ethical grounds                  |                                 |
+---------------------+---------------------------+-----------------------------------------------+---------------------------------+
| `NetBSD`_           | Restricted                | LLM-generated code classified as "tainted";   | Cautions, approval-gated        |
|                     |                           | requires explicit core developer approval     |                                 |
|                     |                           | before submission                             |                                 |
+---------------------+---------------------------+-----------------------------------------------+---------------------------------+
| `FreeBSD`_          | Under development         | Policy in progress; AI permitted for          | Cautious, differentiated by     |
|                     |                           | docs/translations; code generation paused due | use case                        |
|                     |                           | to license concerns                           |                                 |
+---------------------+---------------------------+-----------------------------------------------+---------------------------------+
| `Linux Foundation`_ | Permitted                 | AI-generated code welcome; contributors must  | Open, responsibility-based      |
|                     |                           | verify tool terms align with project license  |                                 |
|                     |                           | and IP policies                               |                                 |
+---------------------+---------------------------+-----------------------------------------------+---------------------------------+

.. _Linux Kernel: https://docs.kernel.org/process/coding-assistants.html
.. _QEMU: https://www.qemu.org/docs/master/devel/code-provenance.html
.. _Gentoo Linux: https://wiki.gentoo.org/wiki/Project:Council/AI_policy
.. _NetBSD: https://www.netbsd.org/developers/commit-guidelines.html
.. _FreeBSD: https://www.theregister.com/2025/09/03/freebsd_project_update_no_ai/
.. _Linux Foundation: https://www.linuxfoundation.org/legal/generative-ai

C.1 Key Takeaways for TYPO3
---------------------------

Several patterns emerge from this analysis that inform the recommended TYPO3 approach. First, the projects closest to TYPO3 in character, meaning those that balance enterprise reliability with developer productivity, tend to favor transparency-based models over outright bans. The Linux kernel's Assisted-by disclosure approach, which keeps DCO sign-off human-only while requiring AI tools to be named, offers a well-tested template. Second, the legal landscape around AI-generated code and copyright remains unsettled internationally, which means any policy must be adaptable. Third, the Developer Certificate of Origin (DCO), while foundational, was not designed for an era of AI-assisted development and may require supplementary guidance rather than fundamental revision.

TYPO3 occupies a particular position in this landscape: it is enterprise CMS infrastructure used in mission-critical applications, but it is also a web-oriented ecosystem where development velocity matters. This suggests a moderate, transparency-focused policy that is neither as restrictive as QEMU's ban nor as laissez-faire as the general Linux Foundation guidance.

C.2 Empirical Research on AI Code Quality
-----------------------------------------

Beyond stated policy positions, the design of this policy was informed by empirical research into the quality and longevity of AI-generated code. A `survival analysis study <https://arxiv.org/abs/2601.16809>`_ of over 200,000 code units across 201 open source projects found that AI-authored code was modified less frequently than human code (Hazard Ratio 0.842), while a separate `analysis of 470 pull requests <https://www.coderabbit.ai/blog/state-of-ai-vs-human-code-generation-report>`_ found that AI-generated code contained roughly 1.7 times more issues than human-written code. These findings reinforce the importance of thorough human review regardless of the policy's permissive approach to AI tool usage.

C.3 Ongoing Developments
------------------------

The TYPO3 Association will continue to monitor developments in this space, including emerging machine-readable conventions for disclosing AI involvement in source code, potential updates to the `Developer Certificate of Origin <https://developercertificate.org/>`_, and evolving case law regarding the copyright status of AI-generated outputs, such as the U.S. Copyright Office's `report on the copyrightability of AI-generated material <https://www.copyright.gov/ai/Copyright-and-Artificial-Intelligence-Part-2-Copyrightability-Report.pdf>`_.
