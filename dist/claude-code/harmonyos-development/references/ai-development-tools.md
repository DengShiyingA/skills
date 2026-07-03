# HarmonyOS AI Development Tools

Use this reference for DevEco Code, DevEco CLI, Agent Framework Kit, app Skills, Intents Kit, A2A, and HarmonyOS 7 AI-assisted development questions.

## Tool selection

| Need | Prefer |
|---|---|
| Full IDE editing, preview, profiling, signing, emulator, and graphical debugging | DevEco Studio |
| Agent-led HarmonyOS implementation and iterative build/run/verify/fix workflows | DevEco Code |
| Scriptable project, build, check, device, and debugging actions for Agents or CI/CD | DevEco CLI |
| General-purpose third-party coding Agent | Its native workflow plus DevEco CLI/Hvigor/HDC and this skill |

DevEco Code is a HarmonyOS-focused coding Agent, while DevEco CLI is the execution layer designed for command-line automation and Agent invocation. Neither changes the production SDK baseline: use API 24 Release by default and API 26 Beta1 only for preview/adaptation work.

## Agent capability boundaries

| Capability | Purpose |
|---|---|
| Agent Framework Kit | Let an app actively launch system Agent combinations through UI controls |
| Intents Kit | Declare app or atomic-service functions as system-recognizable intents |
| ArkTS script-based app Skill | Expose app business capabilities to system intelligent entry points through a declared contract |
| Device-side A2A | Connect an app-side Agent with system Agents using registered components, authenticated bidirectional communication, and interactive UI |
| AgentCard | Present Agent-related content or interaction through supported card capabilities |

Do not use these names interchangeably. First identify whether the user needs UI-triggered Agent invocation, intent exposure, an app Skill, Agent-to-Agent communication, or card presentation.

## HarmonyOS 7 capability notes

- Skill Vibe Coding assists app Skill development, debugging, review, and publishing.
- Visual AI, 3DGS, spatial-audio nodes, app/game quick start, cold-start network preconnection, QUIC, weak-network live-stream optimization, and LTPO variable frame rate are highlighted HarmonyOS 7 capability areas.
- Treat marketing-level capability descriptions as discovery signals, not stable API signatures. Verify the API 26 SDK reference, device category, permissions, and feature availability before generating production code.
- For AGC cloud debugging, filter remote devices by API 26 or system version `7.0.0.23` when validating HarmonyOS 7 compatibility.

## Answer rules

1. State whether the request is about DevEco Studio, DevEco Code, DevEco CLI, or a third-party Agent.
2. Keep API 24 production guidance separate from API 26 Beta preview guidance.
3. Name the exact Agent capability layer instead of using generic terms such as "HarmonyOS Agent API."
4. Do not invent DevEco CLI command names. Use installed-tool help or official documentation for exact commands and flags.
5. For device-dependent capabilities such as LTPO or spatial audio, require SDK and hardware support verification.
