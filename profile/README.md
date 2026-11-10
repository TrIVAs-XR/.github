# R-AIMS Agents

Research on transparent, responsible and explainable embodied AI agents in VR/AR, evaluated in user studies. The XAI Companion is an Intelligent Virtual Agent built as a reusable study platform: one codebase serves every study, and study conditions are configuration.

## How the repositories fit together

![The Unity client exchanges audio and data with the Pipecat agent in XAI-Companion-Backend through the LiveKit server. In the client, the agent package from the public XAI-Companion-XR repository is used both by its Rocketbox demo and by the study project in the private XAI-Companion-Studies repository.](overview.svg)

| Repository | Visibility | Contents |
|---|---|---|
| [XAI-Companion-Backend](https://github.com/R-AIMS-Agents/XAI-Companion-Backend) | Public, MIT | Python backend: Pipecat orchestrates speech recognition, the language model and speech synthesis, and talks to the Unity client over LiveKit. |
| [XAI-Companion-XR](https://github.com/R-AIMS-Agents/XAI-Companion-XR) | Public, MIT | Unity project with the agent as a package (`com.r-aims-agents.xai-companion`): LiveKit connection, conversational state, lip sync, blinking, gaze and a debug panel. Its Rocketbox Agent sample is a complete XR demo with an open avatar, so the backend and this repository together are a working system. |
| XAI-Companion-Studies | Private | Unity project for the user studies. It uses the agent package from XAI-Companion-XR and adds the study avatar, scenes and scenarios. |

The agent code exists once, in XAI-Companion-XR. The study project references the package from a checkout next to it, so changes to the agent reach both the public demo and the studies.

## Why XAI-Companion-Studies is private

The study project is built on commercially licensed assets, among them a Reallusion Character Creator avatar and Unity Asset Store content, whose licences do not allow redistributing their files. The study scenes and scenarios are built from these assets, so they stay private with them. Everything else is public: the agent code lives in XAI-Companion-XR, and its Rocketbox avatar ([Microsoft Rocketbox](https://github.com/microsoft/Microsoft-Rocketbox), MIT) stands in for the licensed one.
