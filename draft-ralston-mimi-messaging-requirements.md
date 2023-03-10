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

This document describes a set of requirements for messaging services to interoperate.

These requirements are independent of any particular protocol or messaging service,
describing the set of features an interoperable messaging service should support.
Services should expect to go beyond the requirements listed here, as MIMI's future
content format evolves.

--- middle

# Introduction

MIMI's charter seeks to establish an extensible set of messaging features which make
use of a future content format published by MIMI. The charter also states that MIMI will
use End-to-End Encryption (E2EE), and that the content format must support E2EE.

This document describes a possible set of features that messaging services should support.
By extension, it also includes what MIMI should support in its future content format.
This document also explores extensibility by contrasting a minimum and maximum feature
set for interoperability over MIMI.

# Minimum Feature Set

The following are the minimum features for an interoperable messaging service:

* Encryption, as required by MIMI's charter, and all associated features (device tracking, etc).
* Conversation history for search, scrollback, and filling gaps between messaging services.
* Text and rich text to represent nearly all features persisted to the conversation history.
* Ability to redact, remove, or delete a message, both as an individual and as a room moderator.
* Invite, kick, ban, and leave membership states within a conversation.
* Display names and avatars for users, to allow for personalization beyond their identifier or
  username.
* Direct messaging, or conversations of exactly 2 users. The underlying protocol might choose
  to treat DMs no different from multi-user conversations, though messaging services might
  apply semantics to represent DMs usefully to users.
* Differentiation between users and their abilities. For example, roles for Moderators, Admins,
  etc.

# Maximum Feature Set

This list is not exhaustive, but outlines some examples for what the content format should be
capable of supporting. The features that messaging services currently support are:

* Names, topics/descriptions, and avatars for conversations for personalization. Messaging
  services which don't support these aesthetic features would ignore them.
* Read receipts/indicators when others in the room have read the message. If a messaging service
  doesn't support them, that service would not produce receipts and ignore received receipts.
  This is a safe failure mode for the feature.
* Typing notifications when others in the room are writing a message. Like read receipts, services
  have the same safe failure mode.
* Presence or online state. Like read receipts or typing notifications, presence has the same safe
  fallback mode.
* Images, videos, files, and audio in messages. The content format would specify a fallback to
  (rich) text to support messaging services that are primarily text-based, such as by specifying
  a URL for users to click on to view the relevant media. Voice messages can be represented as
  audio file uploads with minor decoration metadata in the content format.
* Replies (also called "rich quoting") to reference specific messages or parts of messages. A
  content format specification might define a fallback format to ensure messaging services that
  do not support replies can still render something which looks vaguely like a reply.
* Threads to organize a conversation. A content format specification might define a fallback
  to Replies to keep a reader's context in tact when using a messaging service that doesn't
  support threads.
* VoIP. Messaging services which don't support VoIP could be asked to say "a call is happening,
  but you can't join on this device" under a content format, or, if the conference protocol
  allows, a link for the user to click and join the call externally.
* Message editing. A content format could define a fallback which references the edited message
  with a reply and using a difference syntax to highlight applicable changes.
* Reactions. A content format might decide to use replies to associate an emoji reaction with
  a given message, or simply as nothing.

As implied above, a future content format document would be responsible for describing the exact
details of how features fall back, if at all. This document offers non-binding suggestions.

## Moderation and Personal Safety Functionality

Currently out of scope for MIMI, moderation, anti-spam, etc functionality would likely be considered
part of the "Maximum Feature Set". A suitable protocol could support functionality such as ignoring
or blocking individual users, "who can send invites to me" controls, and similar features without
needing to have a specific content format specification necessarily. For example, preventing invites
from being received could simply be a rejected action over the delivery and transport layer.

# Security Considerations

Security considerations for these features would be handled by other documents, such as a content
format document.

# IANA Considerations

This document has no IANA actions.


--- back
