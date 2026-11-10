# R-AIMS Agents

**An Intelligent Virtual Agent (IVA) pipeline built for developing and studying trustworthy IVAs in XR.**

The XAI Companion is an embodied AI agent in VR/AR for user studies on transparent, responsible and explainable agents: one codebase serves every study, and study conditions are configuration. It is developed at HAW Hamburg in the [XRi Group](https://xri.inf.haw-hamburg.de/) (XR Interaction Research) and [R-AIMS](https://raims.haw-hamburg.de/) (Responsible Advanced Intelligent Methodologies and Skills Lab).

## How the repositories fit together

![The Unity client exchanges audio and data with the Pipecat agent in XAI-Companion-Backend through the LiveKit server. In the client, the agent package from the public XAI-Companion-XR repository is used both by its Rocketbox demo and by the study project in the private XAI-Companion-Studies repository.](overview.svg)

| Repository | Contents |
|---|---|
| [XAI-Companion-Backend](https://github.com/R-AIMS-Agents/XAI-Companion-Backend) | Python backend: Pipecat orchestrates speech recognition, the language model and speech synthesis, and talks to the Unity client over LiveKit. |
| [XAI-Companion-XR](https://github.com/R-AIMS-Agents/XAI-Companion-XR) | Unity project with the agent as a package (`com.r-aims-agents.xai-companion`): LiveKit connection, conversational state, lip sync, blinking, gaze and a debug panel. Its Rocketbox Agent sample is a complete XR demo with an open avatar, so the backend and this repository together are a working system. |
| XAI-Companion-Studies (private) | Unity project for the user studies. It uses the agent package from XAI-Companion-XR and adds the study avatar, scenes and scenarios. |

The agent code exists once, in XAI-Companion-XR. The study project references the package from a checkout next to it, so changes to the agent reach both the public demo and the studies.

## Try it

The two public repositories together run the agent in VR with an open avatar. You need Windows, Unity 6.3 or newer, a PC VR headset on an OpenXR runtime, a microphone and API keys for the speech and language models.

1. Set up [XAI-Companion-Backend](https://github.com/R-AIMS-Agents/XAI-Companion-Backend#setup) as its README describes.
2. Open [XAI-Companion-XR](https://github.com/R-AIMS-Agents/XAI-Companion-XR#getting-started) in Unity and import its Rocketbox Agent sample.
3. Start the backend with the `chat` scenario, then open the demo scene and press Play.

   ```powershell
   uv run python -m agent.run --scenario chat
   ```

## Availability

The agent is fully open source under the MIT licence: the backend in XAI-Companion-Backend, and the Unity client in XAI-Companion-XR with an open avatar from [Microsoft Rocketbox](https://github.com/microsoft/Microsoft-Rocketbox) (MIT). XAI-Companion-Studies uses commercially licensed assets, including a Reallusion Character Creator avatar and Unity Asset Store content, whose licences do not permit redistribution. The study scenes and scenarios depend on these assets and are therefore not published.

## Contact

Through the [XRi Group](https://xri.inf.haw-hamburg.de/) at HAW Hamburg.
