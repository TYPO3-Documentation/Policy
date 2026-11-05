:navigation-title: 08-20 Certificate Server
..  include:: /Includes.rst.txt
..  _t3a-board-decision-2024-08-20-certificate-server:

=============================================================================================================
Board Decision: Membership Benefits: New membership badges + detail page + trust signal + badge / cert server
=============================================================================================================

:Proposed at: 20 August 2024
:Decision owner: `Boris Hinzer`_
:Decision status: ✅ Accepted, with **3 yes, 3 no and 1 abstain**; the tie was broken by the casting vote of the Chairman

Attendance and voting
=====================

========================  ============  ==========
Board Member              Attendance    Vote
========================  ============  ==========
`Olivier Dobberkau`_      In meeting    ✅ Yes (casting vote)
`Stefan Busemann`_        In meeting    ❌ No
`Boris Hinzer`_           Remote        ✅ Yes
`Rachel Foucard`_         In meeting    ⚪ Abstain
`Susi Moog`_              Remote        ❌ No
`Tymoteusz Motylewski`_   Remote        ❌ No
`Thomas Maroschik`_       Remote        ✅ Yes
========================  ============  ==========

.. _Olivier Dobberkau: https://my.typo3.org/u/oli4
.. _Stefan Busemann: https://my.typo3.org/u/stefan.busemann
.. _Boris Hinzer: https://my.typo3.org/u/web-vision
.. _Rachel Foucard: https://my.typo3.org/u/rakel
.. _Susi Moog: https://my.typo3.org/u/psychomieze
.. _Tymoteusz Motylewski: https://my.typo3.org/u/tmotylewski
.. _Thomas Maroschik: https://my.typo3.org/u/tmaroschik

Decision description
====================

Facts/Problem
-------------

**General information:** To make our memberships more attractive, the decision owner would like to introduce real benefits for different membership levels.

**Proposed benefit:**

- Every TCCx **certified person** should be able to access and share their certificates (e.g. on LinkedIn).
- Each certificate shall be downloadable directly as PDF.
- Printing and sending of paper certificates would become obsolete.

**Proposed memberships:**

- Agency: Community, Bronze, Silver, Gold, Platinum
- Academic: Silver (to be discussed), Gold

Objective
---------

- Making our memberships more interesting.
- Increase in memberships.

Obligations to cooperate
------------------------

`VirtualBadge <https://www.virtualbadge.io>`__, an external partner offering an API and certificate server.

Financial and human resources impacts
-------------------------------------

- VirtualBadge: 3,123 EUR per year
- Integration via webhook to the API: maybe 1-2 person days from the typo3.org team (Thomas Löffler), plus listing adjustments.

Resolution/Petitum
------------------

Shall we provide a certificate server for TYPO3 Certified Persons?

Discarded alternatives
----------------------

None

Attachments
-----------

[Link to VirtualBadge offer (board internal)]

Comments
--------

1. `Rachel Foucard`_: "Since a certification is bound to a person and not a company, should the related membership be the community and bronze only? Would it be interesting to propose this benefit for bronze membership only to try to 'transform' community in bronze? What happens (technically) if I cancel my membership?"
2. `Tymoteusz Motylewski`_: "Do we need a cert server to provide the benefits? Isn't it just about providing a PDF to the certified person? In other words, can we deliver the same benefits without dependency on a 3rd party service?"
3. `Boris Hinzer`_: "Yes. But then you still can't embed it in LinkedIn or link it on your own site / profile."
4. `Tymoteusz Motylewski`_: "On LinkedIn, when you are adding certifications, you can add an image, and also a 'Credential URL', which then is used as a link to verify the person has a certificate on the issuer side. Neither image nor credential URL are required fields. I would prefer having this kind of profile being part of typo3.org instead of a 3rd party system."
5. `Boris Hinzer`_: "And who should build it and when? And again we are going into a 'Not invented here'. I strongly doubt that we can build it faster and cheaper in that way."
6. `Olivier Dobberkau`_: "Let us give it a try for one year."
