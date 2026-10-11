# Research Portfolio

**How robot models turn perception into action—and how those technical choices shape products and markets.**

Independent research and writing by **Theodore Ouyang**. These reports connect mathematical mechanisms with practical questions about control, deployment, and product strategy.

## Robot control: what matters between perception and action?

My comparison starts with three questions: what is the model trained to predict, what representation reaches the action generator, and what computation remains when the robot runs?

This reveals a spectrum that the labels “VLA” and “world-action model” often hide. DreamZero jointly generates future video and actions. VPP uses predictive visual features without fully drawing the future. Fast-WAM retains a single-pass world encoder, while GigaWorld-Policy makes action generation independent of its future-video branch.

The useful distinction is where future prediction enters the system. Learning from visual dynamics can shape a policy even when that policy generates only actions at deployment. That changes how we should compare architectures, latency, and the value of world modeling.

[Read the comparison](articles/2026-08-03-from-vision-and-instructions-to-robot-actions/README.en.md) · [Chinese edition](articles/2026-08-03-from-vision-and-instructions-to-robot-actions/README.zh-CN.md)

## π₀: the interface between semantics and continuous control

My reading of π₀ follows the mechanism from conditional flow matching to action chunks and real-world feedback. The action expert reads internal visual-language representations, generates a continuous action sequence, executes a prefix, and replans from a new observation.

I argue that the durable design choice is the interface between a general semantic backbone and a continuous-control expert. The equations explain how actions are generated; the execution loop explains how the robot stays responsive. This also points toward a complementary role for world models in planning and consequence evaluation—a direction developed in my analysis.

[Read the technical walkthrough](research/2026-08-02-pi0-vla-flow/README.en.md) · [Chinese edition](research/2026-08-02-pi0-vla-flow/README.zh-CN.md)

## World models: delivery is becoming part of the competition

The Manifold landscape study examines World Labs, Odyssey, Runway, Decart, and NVIDIA Cosmos 3 using public information as of July 14, 2026.

My conclusion is that competition extends beyond visual model quality to APIs, runtimes, deployment, integration, data rights, and total cost. Publicly priced services, controlled access, and downloadable components create different paths to adoption. I compare them by what an external user can obtain and build with, then translate those differences into questions about standard delivery, shared validation, and deployment rights.

[Read the study](research/2026-08-03-manifold-world-model-landscape/README.en.md) · [Chinese edition](research/2026-08-03-manifold-world-model-landscape/README.zh-CN.md) · [Presentation](research/2026-08-03-manifold-world-model-landscape/source-snapshot/archive/manifold-world-model-landscape/10_deck/manifold_world_model_landscape_v1_4.pptx)

[Research index](research/README.md) · [Article index](articles/README.md) · [Source materials](research/2026-08-03-manifold-world-model-landscape/source-snapshot/README.md) · [Reuse terms](research/2026-08-03-manifold-world-model-landscape/source-snapshot/NOTICE.md)
