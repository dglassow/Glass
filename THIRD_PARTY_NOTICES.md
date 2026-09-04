# Third-party notices

Glass incorporates material derived from OpenMausBot, which is licensed under the Apache License, Version 2.0.
The OpenMausBot NOTICE and the full license text are reproduced below.
Every Glass file that carries derived material starts with a provenance header naming the upstream path, so the origin of each lifted file is visible in the file itself.
The derived-files section at the end of this document is generated from those headers by `tests/p10-legal.mjs`, which also fails when a header is missing from the list or when upstream product tokens leak into the tree.

## Provenance header

For `.mjs`, `.ts`, and `.rs` files the header is the first comment in the file (after the shebang, when there is one):

```
// Derived from OpenMausBot <path> (Apache-2.0). Copyright 2026 Milind Soni and OpenMausBot contributors. Modified for Glass.
```

For CSS the same text rides in a block comment:

```
/* Derived from OpenMausBot <path> (Apache-2.0). Copyright 2026 Milind Soni and OpenMausBot contributors. Modified for Glass. */
```

`<path>` is the file's path inside the OpenMausBot repository at the revision it was lifted from.
When one Glass file consolidates several upstream files, `<path>` is a comma-separated list of those paths on the same line.
The header is always a single line and must appear within the first five lines of the file.

## OpenMausBot (Apache-2.0)

### NOTICE

```
OpenMausBot
Copyright 2026 Milind Soni and OpenMausBot contributors

OpenMausBot was relicensed from the MIT License to the Apache License,
Version 2.0, with the consent of all contributors whose copyright was
incorporated before the transition.
```

### Apache License, Version 2.0

```

                                 Apache License
                           Version 2.0, January 2004
                        http://www.apache.org/licenses/

   TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION

   1. Definitions.

      "License" shall mean the terms and conditions for use, reproduction,
      and distribution as defined by Sections 1 through 9 of this document.

      "Licensor" shall mean the copyright owner or entity authorized by
      the copyright owner that is granting the License.

      "Legal Entity" shall mean the union of the acting entity and all
      other entities that control, are controlled by, or are under common
      control with that entity. For the purposes of this definition,
      "control" means (i) the power, direct or indirect, to cause the
      direction or management of such entity, whether by contract or
      otherwise, or (ii) ownership of fifty percent (50%) or more of the
      outstanding shares, or (iii) beneficial ownership of such entity.

      "You" (or "Your") shall mean an individual or Legal Entity
      exercising permissions granted by this License.

      "Source" form shall mean the preferred form for making modifications,
      including but not limited to software source code, documentation
      source, and configuration files.

      "Object" form shall mean any form resulting from mechanical
      transformation or translation of a Source form, including but
      not limited to compiled object code, generated documentation,
      and conversions to other media types.

      "Work" shall mean the work of authorship, whether in Source or
      Object form, made available under the License, as indicated by a
      copyright notice that is included in or attached to the work
      (an example is provided in the Appendix below).

      "Derivative Works" shall mean any work, whether in Source or Object
      form, that is based on (or derived from) the Work and for which the
      editorial revisions, annotations, elaborations, or other modifications
      represent, as a whole, an original work of authorship. For the purposes
      of this License, Derivative Works shall not include works that remain
      separable from, or merely link (or bind by name) to the interfaces of,
      the Work and Derivative Works thereof.

      "Contribution" shall mean any work of authorship, including
      the original version of the Work and any modifications or additions
      to that Work or Derivative Works thereof, that is intentionally
      submitted to Licensor for inclusion in the Work by the copyright owner
      or by an individual or Legal Entity authorized to submit on behalf of
      the copyright owner. For the purposes of this definition, "submitted"
      means any form of electronic, verbal, or written communication sent
      to the Licensor or its representatives, including but not limited to
      communication on electronic mailing lists, source code control systems,
      and issue tracking systems that are managed by, or on behalf of, the
      Licensor for the purpose of discussing and improving the Work, but
      excluding communication that is conspicuously marked or otherwise
      designated in writing by the copyright owner as "Not a Contribution."

      "Contributor" shall mean Licensor and any individual or Legal Entity
      on behalf of whom a Contribution has been received by Licensor and
      subsequently incorporated within the Work.

   2. Grant of Copyright License. Subject to the terms and conditions of
      this License, each Contributor hereby grants to You a perpetual,
      worldwide, non-exclusive, no-charge, royalty-free, irrevocable
      copyright license to reproduce, prepare Derivative Works of,
      publicly display, publicly perform, sublicense, and distribute the
      Work and such Derivative Works in Source or Object form.

   3. Grant of Patent License. Subject to the terms and conditions of
      this License, each Contributor hereby grants to You a perpetual,
      worldwide, non-exclusive, no-charge, royalty-free, irrevocable
      (except as stated in this section) patent license to make, have made,
      use, offer to sell, sell, import, and otherwise transfer the Work,
      where such license applies only to those patent claims licensable
      by such Contributor that are necessarily infringed by their
      Contribution(s) alone or by combination of their Contribution(s)
      with the Work to which such Contribution(s) was submitted. If You
      institute patent litigation against any entity (including a
      cross-claim or counterclaim in a lawsuit) alleging that the Work
      or a Contribution incorporated within the Work constitutes direct
      or contributory patent infringement, then any patent licenses
      granted to You under this License for that Work shall terminate
      as of the date such litigation is filed.

   4. Redistribution. You may reproduce and distribute copies of the
      Work or Derivative Works thereof in any medium, with or without
      modifications, and in Source or Object form, provided that You
      meet the following conditions:

      (a) You must give any other recipients of the Work or
          Derivative Works a copy of this License; and

      (b) You must cause any modified files to carry prominent notices
          stating that You changed the files; and

      (c) You must retain, in the Source form of any Derivative Works
          that You distribute, all copyright, patent, trademark, and
          attribution notices from the Source form of the Work,
          excluding those notices that do not pertain to any part of
          the Derivative Works; and

      (d) If the Work includes a "NOTICE" text file as part of its
          distribution, then any Derivative Works that You distribute must
          include a readable copy of the attribution notices contained
          within such NOTICE file, excluding those notices that do not
          pertain to any part of the Derivative Works, in at least one
          of the following places: within a NOTICE text file distributed
          as part of the Derivative Works; within the Source form or
          documentation, if provided along with the Derivative Works; or,
          within a display generated by the Derivative Works, if and
          wherever such third-party notices normally appear. The contents
          of the NOTICE file are for informational purposes only and
          do not modify the License. You may add Your own attribution
          notices within Derivative Works that You distribute, alongside
          or as an addendum to the NOTICE text from the Work, provided
          that such additional attribution notices cannot be construed
          as modifying the License.

      You may add Your own copyright statement to Your modifications and
      may provide additional or different license terms and conditions
      for use, reproduction, or distribution of Your modifications, or
      for any such Derivative Works as a whole, provided Your use,
      reproduction, and distribution of the Work otherwise complies with
      the conditions stated in this License.

   5. Submission of Contributions. Unless You explicitly state otherwise,
      any Contribution intentionally submitted for inclusion in the Work
      by You to the Licensor shall be under the terms and conditions of
      this License, without any additional terms or conditions.
      Notwithstanding the above, nothing herein shall supersede or modify
      the terms of any separate license agreement you may have executed
      with Licensor regarding such Contributions.

   6. Trademarks. This License does not grant permission to use the trade
      names, trademarks, service marks, or product names of the Licensor,
      except as required for reasonable and customary use in describing the
      origin of the Work and reproducing the content of the NOTICE file.

   7. Disclaimer of Warranty. Unless required by applicable law or
      agreed to in writing, Licensor provides the Work (and each
      Contributor provides its Contributions) on an "AS IS" BASIS,
      WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or
      implied, including, without limitation, any warranties or conditions
      of TITLE, NON-INFRINGEMENT, MERCHANTABILITY, or FITNESS FOR A
      PARTICULAR PURPOSE. You are solely responsible for determining the
      appropriateness of using or redistributing the Work and assume any
      risks associated with Your exercise of permissions under this License.

   8. Limitation of Liability. In no event and under no legal theory,
      whether in tort (including negligence), contract, or otherwise,
      unless required by applicable law (such as deliberate and grossly
      negligent acts) or agreed to in writing, shall any Contributor be
      liable to You for damages, including any direct, indirect, special,
      incidental, or consequential damages of any character arising as a
      result of this License or out of the use or inability to use the
      Work (including but not limited to damages for loss of goodwill,
      work stoppage, computer failure or malfunction, or any and all
      other commercial damages or losses), even if such Contributor
      has been advised of the possibility of such damages.

   9. Accepting Warranty or Additional Liability. While redistributing
      the Work or Derivative Works thereof, You may choose to offer,
      and charge a fee for, acceptance of support, warranty, indemnity,
      or other liability obligations and/or rights consistent with this
      License. However, in accepting such obligations, You may act only
      on Your own behalf and on Your sole responsibility, not on behalf
      of any other Contributor, and only if You agree to indemnify,
      defend, and hold each Contributor harmless for any liability
      incurred by, or claims asserted against, such Contributor by reason
      of your accepting any such warranty or additional liability.

   END OF TERMS AND CONDITIONS

   APPENDIX: How to apply the Apache License to your work.

      To apply the Apache License to your work, attach the following
      boilerplate notice, with the fields enclosed by brackets "[]"
      replaced with your own identifying information. (Don't include
      the brackets!)  The text should be enclosed in the appropriate
      comment syntax for the file format. We also recommend that a
      file or class name and description of purpose be included on the
      same "printed page" as the copyright notice for easier
      identification within third-party archives.

   Copyright [yyyy] [name of copyright owner]

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```

## Cua Driver (MIT)

Added when the driver is bundled (Phase 10 M3); see third_party/cua-driver/NOTICES.md

## Derived files

<!-- derived-files: maintained by tests/p10-legal.mjs --check -->

- `packages/botd/src/approvals.ts` (from `server/peer-approval.ts`)
- `packages/botd/src/ask.ts` (from `server/index.ts`)
- `packages/botd/src/attachments.ts` (from `server/attachments.ts`)
- `packages/botd/src/auto-approve.ts` (from `server/auto-approve.ts`)
- `packages/botd/src/bot-cwd.ts` (from `server/bot-cwd.ts`)
- `packages/botd/src/comms.ts` (from `server/comms-visibility.ts`)
- `packages/botd/src/computer/control.ts` (from `server/computer-control.ts`)
- `packages/botd/src/computer/frame-gate.ts` (from `server/screen-frame-gate.ts`)
- `packages/botd/src/computer/lease.ts` (from `server/local-vm-lease.ts`)
- `packages/botd/src/computer/local-computer.ts` (from `server/local-computer.ts`)
- `packages/botd/src/computer/observation.ts` (from `server/computer-observation.ts`)
- `packages/botd/src/computer/private-capture.ts` (from `server/private-screen-capture.ts`)
- `packages/botd/src/decision-log.ts` (from `server/decision-log.ts`)
- `packages/botd/src/delegate.ts` (from `server/index.ts`)
- `packages/botd/src/delegations.ts` (from `server/delegations.ts`)
- `packages/botd/src/events.ts` (from `server/contracts.ts`)
- `packages/botd/src/fold.ts` (from `server/index.ts`)
- `packages/botd/src/goal-run.ts` (from `server/group-goal-run.ts`)
- `packages/botd/src/guards.ts` (from `server/turn-dispatch-guard.ts`, `server/turn-watchdog.ts`, `server/room-turn-timeout.ts`)
- `packages/botd/src/message-db.ts` (from `server/message-db.ts`)
- `packages/botd/src/names.ts` (from `server/names.ts`)
- `packages/botd/src/notify.ts` (from `server/notify.ts`)
- `packages/botd/src/peer-approval-key.ts` (from `server/peer-approval-key.ts`)
- `packages/botd/src/permission-broker.ts` (from `server/drivers/claude.ts`)
- `packages/botd/src/prompts.ts` (from `server/chief-of-staff.ts`, `server/member-turn.ts`)
- `packages/botd/src/proxies/agents-proxy.ts` (from `server/drivers/agents-proxy.ts`)
- `packages/botd/src/proxies/permission-proxy.ts` (from `server/permission-proxy.ts`)
- `packages/botd/src/queues.ts` (from `server/steer-queue.ts`, `server/channel-queue.ts`)
- `packages/botd/src/room-cwd.ts` (from `server/room-cwd.ts`)
- `packages/botd/src/rooms.ts` (from `server/index.ts`)
- `packages/botd/src/routine-requests.ts` (from `server/routine-requests.ts`)
- `packages/botd/src/routines.ts` (from `server/routines.ts`)
- `packages/botd/src/shared/bot-avatar.ts` (from `shared/bot-avatar.ts`)
- `packages/botd/src/shared/bot-profile.ts` (from `shared/bot-profile.ts`)
- `packages/botd/src/shared/credential-request.ts` (from `shared/credential-request.ts`)
- `packages/botd/src/shared/group-goal-run.ts` (from `shared/group-goal-run.ts`)
- `packages/botd/src/shared/mascot-bodies.ts` (from `shared/mascot-bodies.ts`)
- `packages/botd/src/shared/routine-request.ts` (from `shared/routine-request.ts`)
- `packages/botd/src/shared/routine-run.ts` (from `shared/routine-run.ts`)
- `packages/botd/src/shared/skill-request.ts` (from `shared/skill-request.ts`)
- `packages/botd/src/skills-feed.ts` (from `server/skills.ts`)
- `packages/botd/src/store.ts` (from `server/store.ts`)
- `packages/botd/src/thread-events.ts` (from `server/thread-events.ts`)
- `packages/botd/src/turn-context.ts` (from `server/turn-context.ts`)
- `packages/botd/src/turns.ts` (from `server/index.ts`)
- `packages/botd/src/util/atomic.ts` (from `server/atomic.ts`)
- `packages/botd/src/util/env-path.ts` (from `server/env-path.ts`)
- `packages/botd/src/util/procs.ts` (from `server/procs.ts`)
- `packages/botd/src/util/redact.ts` (from `server/redact.ts`)
- `packages/botd/src/workspace.ts` (from `server/workspace.ts`)
- `packages/desktop/glass-cua-host.mjs` (from `electron/cua.mjs`, `electron/cua-connection.cjs`, `electron/cua-linux-runtime.cjs`)
- `packages/desktop/glass-cua-linux.mjs` (from `electron/capabilities.cjs`, `electron/cua-linux.cjs`)
- `packages/desktop/prepare-cua.sh` (from `scripts/prepare-cua.mjs`, `scripts/cua-linux-release.mjs`)
- `packages/sessiond/src/mounts.ts` (from `server/config.ts`)
- `packages/viewer/src/bots-events.ts` (from `src/state/store.tsx`)
- `packages/viewer/src/bots-reducer.ts` (from `src/state/store.tsx`)
- `packages/viewer/src/shell.css` (from `src/styles.css`)
- `packages/viewer/src/skins.ts` (from `src/lib/skins.ts`)
- `tests/fakes/fake-acp-cli.mjs` (from `server/testing/fake-acp-cli.ts`)
- `tests/fakes/fake-claude-cli.mjs` (from `server/testing/fake-claude-cli.ts`)
- `tests/fakes/fake-codex-app-server.mjs` (from `server/testing/fake-codex-app-server.ts`)
