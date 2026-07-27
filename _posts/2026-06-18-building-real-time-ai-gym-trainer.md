---
layout: post
title: "Building a Real-Time AI Gym Trainer"
date: 2026-06-18
tags: [Computer Vision, Android, Fitness AI, MediaPipe]
excerpt: "Lessons from turning a mobile camera into a feedback loop for training."
---

Tenslam Gym started from one practical question: can a phone camera improve movement quality while a person is still in the set?

For this product, detection quality alone is not enough. The system has to close a full loop in near real time:

1. detect pose landmarks
2. estimate exercise state and repetition phase
3. evaluate posture quality
4. return feedback quickly enough to influence the next rep

If this loop is slow or unstable, the product feels disconnected and users stop trusting the feedback.

## System architecture

The current prototype architecture is intentionally simple:

* **On-device pose estimation:** MediaPipe landmarks from camera frames
* **Signal conditioning:** smoothing and temporal filtering to reduce jitter
* **State machine logic:** repetition counting and posture-rule checks
* **Feedback layer:** concise visual cues and counters in-session
* **Session persistence:** lightweight Firebase-backed product state

The non-obvious work is in the transition logic between these stages, especially when inputs are partial or noisy.

## Benchmark frame

The table below is the benchmark frame I use during iteration.

| Metric | Why it matters | Current public status |
|---|---|---|
| End-to-end feedback latency | Determines whether feedback can change user behavior in-session | Measurement in progress |
| Rep-count consistency | Core trust metric for training use | Validation in progress |
| Posture alert precision | Reduces noisy or incorrect corrections | Validation in progress |
| Out-of-frame recovery behavior | Real users move unpredictably | Mitigation in progress |

I am publishing this structure now so future updates can be compared on the same measurement frame.

## Failure modes observed

These are the highest-impact failure classes so far:

* **Partial body visibility:** causes unstable landmark geometry and false transitions
* **Tempo changes:** can trigger double-counting in naive phase boundaries
* **Camera angle drift:** reduces reliability for fixed threshold logic
* **Jitter bursts:** produce posture warnings that feel inconsistent to users

Current mitigation direction:

* temporal smoothing tuned by exercise class
* state-transition hysteresis to reduce flip-flop behavior
* confidence gating before issuing posture alerts

## Product lesson

Real-time fitness AI is a systems reliability problem, not a single-model problem.
Useful behavior comes from coordination across inference, timing, heuristics, UX signaling, and recovery from imperfect inputs.

## Next milestone

The next milestone is a publishable case-study release with:

* measured latency envelope on target devices
* rep-count reliability on selected movement patterns
* explicit failure-mode matrix and mitigation status
