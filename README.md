# Jelly Cloud

This public repository is the GitHub Actions worker for Jelly Cloud. The
private Jelly Cloud Core repository owns the application, request authority,
and result and recovery state. Workflow syntax validation runs on main pushes
and workflow pull requests. The Rust job is disabled until the bridge is configured.

The Rust job validates the bound request using Core's CI control. It fetches
the exact tested commit and revokes its scoped reader token before executing
checks. Core records the actual control and public workflow revisions. Private
build output and GitHub command files are suppressed.

The workflow is adapted from [LibraryHub](https://github.com/cagojeiger/libraryhub/tree/0171e1d237bd714169659d22f3328518ba05cb69) and [Mossden's public CI control](https://github.com/cagojeiger/mossden/tree/7706e75f5e8a1587c454fe9f439c08268dd8eef1)
and is provided under [GPL-3.0](LICENSE).
