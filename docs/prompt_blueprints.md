# Fitrax Multi-Tiered Prompt Engineering Blueprints

This document outlines the systematic prompt engineering architecture and safety guardrails implemented in the **Fitrax** intelligent resistance training decision support system.

To balance scientific reproducibility with the protection of production implementation details, this blueprint details the **four-tier contextualization stack** and domain-specific decision rules governing the system's LLM interactions.

---

## 🏛️ Systematic Prompt Architecture: The 4-Tier Stack

All generative interactions across Fitrax modules—Multimodal Vision Transcription, Intra-Workout Coaching, Dynamic Plan Optimization, and Post-Workout Performance Feedback—are governed by a unified four-tier contextualization pipeline:

```
┌─────────────────────────────────────────────────────────────┐
│ Tier 1: Persona & Evidence-Based Exercise Science Framework │
├─────────────────────────────────────────────────────────────┤
│ Tier 2: Biomechanical Safety & Orthopedic Contraindications │
├─────────────────────────────────────────────────────────────┤
│ Tier 3: Real-Time Dynamic Context & State Immutability      │
├─────────────────────────────────────────────────────────────┤
│ Tier 4: Target Strict JSON Schema & Sanitization Defense   │
└─────────────────────────────────────────────────────────────┘
```

---

### Tier 1: Persona & Exercise Physiology Framework
* **Role Definition:** An elite clinical exercise specialist and resistance training biomechanist adhering to evidence-based resistance training and progressive overload principles (ACSM guidelines).
* **Communication Directives:**
  * Deliver concise, encouraging, and actionable cues during live sessions.
  * Formulate primary conversational responses in fluent Persian (`fa-IR`), appending standard biomechanical nomenclature in parentheses for clarity.
  * Prioritize controlled eccentric cadences, scapular stabilization, and core bracing over maximal load progression.

---

### Tier 2: Biomechanical Safety & Orthopedic Guardrails
* **Objective:** Prevent acute musculoskeletal aggravation and ensure safe movement trajectories.
* **Codified Pathology Rules:**
  1. `scoliosis`: Restricts heavy asymmetric spinal loading; favors bilateral chest-supported rows and dumbbell exercises to maintain structural symmetry.
  2. `back_pain` / `sciatica`: Automatically eliminates compressive axial spinal loads (e.g., heavy Barbell Back Squats and conventional Deadlifts), substituting supported Leg Presses or Chest-Supported Rows.
  3. `shoulder_impingement`: Eliminates vertical overhead pressing ($>90^\circ$ abduction), replacing with neutral-grip dumbbell presses and horizontal cable rows.
  4. `knee_pain` (Patellofemoral): Restricts deep forward knee translation; substitutes deep lunges with Box Squats and hamstring-dominant Romanian Deadlifts.
  5. `wrist_pain`: Prohibits rigid straight-bar curls, recommending neutral-grip dumbbells or ergonomic EZ-curl bars.
  6. `kyphosis` & `lordosis`: Enforces scapular retraction and prohibits excessive hyperextension during compound movements.

---

### Tier 3: Real-Time Dynamic Context & State Immutability
* **Injected Context Vector:**
  * **User Demographics:** Age, gender, body weight, height, and target muscle split.
  * **Active Session Context:** Completed exercises, recorded set weights, repetitions, and qualitative intra-set notes.
  * **Immutable Completed Sets Rule:** Any exercise or set flagged as `is_completed: true` in the client state is declared **strictly immutable**. The model is explicitly prohibited from modifying, re-ordering, or deleting logged progress.
  * **Longitudinal Memory:** Summary performance metrics and fatigue tags across the user's preceding 5 completed routines.

---

### Tier 4: Output Schema & Defense-in-Depth Sanitization
* **Five-Branch Workout Schema Tree:**
  Every prescribed exercise is strictly classified into one of five structured UI component types:
  * `strength`: Discrete weight, set, and repetition tracking.
  * `superset`: Antagonist or compound pairings executed with zero inter-exercise rest.
  * `cardio`: Aerobic elements tracked by duration and perceived intensity.
  * `text_based_sets`: Time-governed or qualitative bodyweight sets (e.g., Planks, Hanging Leg Raises).
  * `simple`: Dynamic joint rotations and static cool-down stretches.
* **Modification Tracking Badges (`aiBadge`):**
  * `null`: Unmodified exercise.
  * `improved`: Load, repetition, or tempo modified via progressive overload.
  * `new`: Added replacement exercise.
  * `deleted`: Truncated exercise due to fatigue or time constraints.
* **Server-Side Sanitization:** Raw model responses are processed through a dedicated sanitizer that strips markdown wrappers, repairs malformed brackets, and validates JSON types before dispatching to the client.


