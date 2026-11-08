# {project-name} — App 4 release image

**This repository holds no application code. Never add a form or server module to App 3.**

It defines the release image every client instance of {project-name} runs: the Anvil App Server at the version Mybizz pins, with `{slug}-app3` (the client app), `{slug}-app2` (`master_template`) and the `m3` theme. It holds the image definition (`Dockerfile`), the container start script, the release checks and the image build workflow, as `spec-client-instance-hosting.md` in `project-library-global` sets out.

The image build stops if App 3 holds any form or server module, or if a release removes, renames or retypes a table or column. A change, even for one client, is made in `{slug}-app1`, tested on the test client instance, and released into `master_template` (Step 42).

This is a public GitHub repository, never an Anvil app. Every document, decision and PDLF record for it is in `{slug}-project-library`.
