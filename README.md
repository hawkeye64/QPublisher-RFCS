# QPublisher-RFCs

## What is an RFC?
The "RFC" (request for comments) process is intended to provide a consistent and controlled path for new features to enter the framework.

Many changes, including bug fixes and documentation improvements can be implemented and reviewed via the normal GitHub pull request workflow.

Some changes though are "substantial", and we ask that these be put through a bit of a design process and produce a consensus among the Vue core team and the community.

## When to follow this process

You need to follow this process if you intend to make "substantial"
changes to one of the projects listed below:

- [QPublisher](https://github.com/hawkeye64/QPublisher)

## The RFC life-cycle

An RFC goes through the following stages:

- **Pending:** when the RFC is submitted as a PR.
- **Active:** when an RFC PR is merged and undergoing implementation.
- **Landed:** when an RFC's proposed changes are shipped in an actual release.
- **Rejected:** when an RFC PR is closed without being merged.

[Pending RFC List](https://github.com/hawkeye64/QPublisher-RFCS/pulls)

## What the process is
- Fork the RFC repo
- Copy the ``0000-template.md`` to ``active-rfcs/0000-my-feature.md``  (where 'my-feature' is descriptive. Don't assign an RFC number yet).
- Fill in the RFC. Put care into the details: RFCs that do not present convincing motivation, demonstrate understanding of the impact of the design, or are disingenuous about the drawbacks or alternatives tend to be poorly-received.
- Submit a pull request.As a pull request the RFC will receive design feedback from the core team member, and the author should be prepared to revise it in response.
- Eventually, the team will decide whether the RFC is a candidate or not.
- An RFC may be accepted at the close of its final comment period. A core team member will merge the RFC's associated pull request, at which point the RFC will become 'active'.

## Implementing an RFC

The author of an RFC is not obligated to implement it. Of course, the
RFC author (like any other developer) is welcome to post an
implementation for review after the RFC has been accepted.

An active RFC should have the link to the implementation PR listed if there is one. Feedback to the actual implementation should be conducted in the implementation PR instead of the original RFC PR.

If you are interested in working on the implementation for an 'active'
RFC, but cannot determine if someone else is already working on it,
feel free to ask (e.g. by leaving a comment on the associated issue).

## Reviewing RFC's

Members of the core team will attempt to review some set of open RFC
pull requests on a regular basis. If a core team member believes an RFC PR is ready to be accepted into active status, they can approve the PR using GitHub's review feature to signal their approval of the RFC.

**QPublisher-RFC process owes its inspiration to the [React RFC process], [Rust RFC process] and [Vuejs RFC process]**

[React RFC process]: https://github.com/reactjs/rfcs
[Rust RFC process]: https://github.com/rust-lang/rfcs
[Vuejs RFC process]: https://github.com/vuejs/rfcs
