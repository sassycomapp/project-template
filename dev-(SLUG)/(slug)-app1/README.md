# {project-name} — App 1

The development workspace. All feature work happens here.

This is a public Anvil code repository. It holds code only. Every document, decision and PDLF record for this app is in `{slug}-project-library`.

| Folder | What it holds |
|---|---|
| `client_code\`, `server_code\`, `theme\`, `anvil.yaml` | The Anvil app, created by Anvil. No agent writes `anvil.yaml`. |
| `theme\assets\docs\` | The published copies of the client-facing guides, served by link from the app. Their sources are in the project library's `guides-local\`. |
| `tests\logic\` | Level 1 tests: the pure logic alone. |
| `tests\integration\` | Level 2 tests: against the local runtime and the Uplink connections. |
| `tests\security\` | Security tests, generated from the app's access matrix. |
| `tests\` | Also `conftest.py`, `pytest.ini` and `ts-config.yaml`, copied from the test suite at Step 11. |
| `scripts\` | Scripts this app needs to run locally. The test suite's own tools stay in `project-library-global\test-suite\tools\` and are never copied here. |

Not committed: `.env` (the local keys, written by David with `ts_local.sh init`), test output and the code graph.
