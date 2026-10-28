# Useless_nos: verification and operations

Reviewed against [default-branch commit be77a3623877](https://github.com/noel-ult/Useless_nos/commit/be77a3623877d8e8094bfdf96e09fd49b8a00560) on 2026-10-28. Start with the [developer guide](PROJECT_GUIDE.md) for installation and architecture, and the [source reference](REFERENCE.md) for exact scripts, configuration readers, routes, and source locations.

## Browser and Windows pointer experiments

For index.html, check pause, chaos/flicker toggles, cursor shape, and ghost count. For Final.py, use a Windows desktop with Tkinter and PyAutoGUI and verify pause/exit before enabling movement.

These are acceptance scenarios for a maintainer to run in the documented environment. Their inclusion is not a claim that live integrations or production credentials were tested during this documentation update.

## Deployment and failure diagnosis

The HTML edition stays inside the browser. Python editions call Windows pointer APIs and should run one at a time in an attended graphical session. test11.py is an interactive prototype, not an automated test.

## Maintaining the contract

When behavior changes, update the guide and examples in the same PR. Check the entry point and working directory before copying commands. Use the linked source readers to distinguish build-time configuration from process environment. For failures, capture the first application error, runtime version, selected mode, and redacted configuration names before later proxy or port errors.

Keep changes tied to evidence: a declared command is not proof it passes, a process health response is not a successful end-to-end workflow, and a historical report describes its own revision. Record actual check results and any unavailable external services in the PR.
