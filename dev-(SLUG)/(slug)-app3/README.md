# {project-name} — App 3

**Never add a form or server module to this app.** It holds only App 1's table definitions, one startup module, the scheduled tasks and its dependency on App 2.

Every client instance runs this app inside the release image, on `master_template` (App 2). A form or server module added here overrides `master_template` for every client, and later fixes to it in `master_template` stop reaching clients. The image build in `{slug}-app4` stops if this app holds one.

A change, even for one client, is made in `{slug}-app1`, tested on the test client instance, and released into `master_template` (Step 42); every client instance receives it through the next release.

This is a public Anvil code repository. It holds code only. Every document, decision and PDLF record for this app is in `{slug}-project-library`.

