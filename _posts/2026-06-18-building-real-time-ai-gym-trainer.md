---
layout: post
title: "Building a Real-Time AI Gym Trainer"
date: 2026-06-18
tags: [Computer Vision, Android, Fitness AI, MediaPipe]
excerpt: "Lessons from turning a mobile camera into a feedback loop for training."
---

Tenslam Gym started from a simple question: can a phone camera help someone train better in real time?

That sounds straightforward until you try to make it feel useful. The app has to see the user, estimate pose, count reps, detect posture problems, and return feedback fast enough that it still feels connected to the movement. Once latency gets too high, the value drops quickly.

The core loop is not just detection. It is feedback.

I wanted the app to do a few things well:

* detect body landmarks reliably enough for common exercises
* count repetitions without being fooled by partial movement
* give posture feedback that is simple to understand
* run acceptably on a mobile device
* keep the interface lightweight so the user focuses on the movement, not the app

MediaPipe was useful because it gave me a practical starting point for pose estimation on device. The real work was in the surrounding logic: smoothing noisy landmarks, deciding what counts as a rep, and reducing false positives when the user moves out of frame or changes tempo.

Firebase helped on the product side. It made it easier to prototype user flows, store lightweight session data, and keep the system moving without building a heavy backend first.

The biggest lesson was that real-time fitness AI is a systems problem, not just a model problem. You need inference, timing, mobile constraints, and user trust to line up at once. If any one of those breaks, the product feels brittle.

That is still the kind of challenge I enjoy most: building something close to the edge of what is practical, then tightening the loop until it feels dependable.
