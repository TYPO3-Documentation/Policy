:navigation-title: 07-09 Policy Governance
..  include:: /Includes.rst.txt
..  _t3a-board-decision-2026-07-09-policy-governance:

===============================================================================
Board Decision: Governance and Change Management in the TYPO3 Policy Repository
===============================================================================

:Start of voting: 9 July 2026
:Voting deadline: 16 July 2026
:Decision owner: `Martin Helmich`_
:Decision status: ✅ Accepted, with **6 yes**

Attendance and voting
=====================

====================  ============  ======
Board Member          Attendance     Vote
====================  ============  ======
`Olivier Dobberkau`_  Asynchronous  ✅ Yes
`Stefan Busemann`_    Asynchronous  ✅ Yes
`Jochen Weiland`_     Asynchronous  ✅ Yes
`Martin Helmich`_     Asynchronous  ✅ Yes
`Jana Höffner`_       Asynchronous  ✅ Yes
`Thomas Maroschik`_   Asynchronous  ✅ Yes
====================  ============  ======

.. _Olivier Dobberkau: https://my.typo3.org/u/oli4
.. _Stefan Busemann: https://typo3.org/team/board/stefan-busemann/
.. _Jochen Weiland: https://my.typo3.org/u/jweiland
.. _Martin Helmich: https://my.typo3.org/u/mhelmich
.. _Jana Höffner: https://my.typo3.org/u/janahh
.. _Thomas Maroschik: https://my.typo3.org/u/tmaroschik

Decision description
====================

Facts/Problem
-------------

In the course of the typo3.org relaunch, the TYPO3 Association bylaws and policies were moved to the https://github.com/TYPO3-Documentation/Policy git repository. However, no approval or change management policies exist for this repository.

This is particularly critical as there are a number of policy and bylaw changes in the coming that may attract broad community interest.

Objective
---------

This proposal aims to provide a clear change management process for TYPO3 Association policies and bylaws, happening in the public and giving broad opportunities for member participation.

Obligations to cooperate
------------------------

- TYPO3 Documentation Team, as they own the policy repository
- TYPO3 Association Board and Business Control Committee, as this change management process requires their active participation


Financial and human resources impacts
-------------------------------------

None.

Resolution/Petitum
------------------

The board resolves to adopt the workflow proposed in `Proposal for Governance and Change Management in the TYPO3 Policy Repository <https://docs.google.com/document/d/1ecjAK-25y22E3XhelGEPV6SRoQjW6pK82Y_pNIlWxKo/edit?tab=t.0#heading=h.v3rpbh68yy7d>`_.

This workflow includes:

- Using the https://github.com/TYPO3-Documentation/Policy repository to govern TYPO3 Association policies and bylaws, and the changes thereof.
- Using Git and GitHub Pull Requests to track changes to these documents.

Rules for Ownership and Changes

- **Owner:**

  - Decisions of ownership are handled by the TYPO3 Association Board. 
  - All policy documents within the repository must specify an owner on line just below the H1 title. It must state who can make changes to it (i.e. “owner”). For example: “This policy can only be changed through a decision by: TYPO3 Association General Assembly.”
  - The TYPO3 Association General Assembly can be represented by Members of the TYPO3 Association Board.

- **Types of changes and approval:** Two types of changes are possible in the decision and review process. No changes can be made to the repository files unless they are handled correctly as one, and only one, of these change types:

  - **Formal changes:** Changes to the meaning of the text. These require formal decisions by the owner in accordance with the owner's decision-making rules. Merging changes require 2 PR approvals by representatives of the owner.
    
    For changes to the Bylaws, this means that each change must be substantiated by a vote of the General Assembly. When changing the Bylaws via a PR, this PR must only be merged if there is a General Assembly protocol that recorded the required vote for this change.
    
  - **Maintenance changes:** Changes that do not change the meaning of the text. For example, correcting a link that is currently leading to a 404 page. These do not require formal decisions by the owner, but PRs must be approved by 1 representative of the owner.

- **Documenting decisions:** All changes must be merged as PRs containing documentation of the decision authorizing the change.

  - **Formal changes:** A separate decision document must be included in the PR. The document should conform to the owner's decision documentation rules. For example, a TYPO3 Association Board decision to change the Reimbursement Regulations can be placed in the Documentation/Association/Board/Decisions folder.
  - **Maintenance changes:** These change decisions can be documented in the commit message.

Discarded alternatives
----------------------

- Move policy and bylaws back into the typo3.org TYPO3 instance. Discarded because Git and GitHub provide better change tracking and governance possibilities.

Attachments
-----------

None

Comments
--------

None