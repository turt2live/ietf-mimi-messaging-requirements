---
title: "Requirements of Interoperable Messaging"
abbrev: "Requirements of an Interoperable Messaging Protocol"
category: info

docname: draft-ralston-mimi-messaging-requirements-latest
submissiontype: IETF  # also: "independent", "IAB", or "IRTF"
number:
date:
consensus: true
v: 3
area: "Applications and Real-Time"
workgroup: "More Instant Messaging Interoperability"
keyword:
 - mimi
 - messaging
 - requirements
 - interoperability
 - minimum
venue:
  group: "More Instant Messaging Interoperability"
  type: "Working Group"
  mail: "mimi@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/mimi/"
  github: "turt2live/ietf-mimi-messaging-requirements"
  latest: "https://turt2live.github.io/ietf-mimi-messaging-requirements/draft-ralston-mimi-messaging-requirements.html"

author:
 -
    fullname: Travis Ralston
    organization: The Matrix.org Foundation C.I.C.
    email: travisr@matrix.org

normative:

informative:


--- abstract

This document describes a set of requirements for messaging services when attempting
to interoperate with another messaging service.

The requirements outlined here are intended to be independent of any particular
protocol or messaging service, instead simply describing the features an interoperable
messaging service should have. Services should be expected to go beyond the requirements
listed in this document, as is anticipated to be possible with MIMI's future content
format.


--- middle

# Introduction

MIMI's charter states that it will identify an extensible baseline set of messaging
features, and specify a content format to allow that feature set to be implemented
interoperably. The charter also states that MIMI will make use of End-to-End Encryption,
and that the content format chosen must support E2EE.

This document describes a possible set of features that all messaging services within
the MIMI scope should support, and by extension what MIMI should support in its content
format. This document additionally touches on extensibility by describing what is considered
to be the absolute minimum a messaging service should support and what would be desirable
for maximum interoperability over MIMI.

# Minimum Feature Set

TODO Section

# Maximum Feature Set

TODO Section

# Security Considerations

TODO Security


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
