# Task 3: Assess a Design for InnovateNow

### Overview
InnovateNow is a platform where users post novel ideas, gather feedback through polls, and analyze demographic data. Below is an assessment of the provided design based on the given requirements.

---

## 1. Does the design meet the software specification?

**Partially**, the design covers key concepts such as ideas, polls, and users. However, it lacks clarity on how the collection of demographic data occurs through polls. There’s no clear mechanism showing how this data is linked to user feedback.

---

## 2. Cohesion and Coupling

- **Low Coupling**: The design shows good separation between key entities (Idea, Poll, User), promoting low coupling. Changes to the poll structure, for instance, wouldn't heavily impact other areas.

- **High Cohesion**: The responsibilities of each class seem focused. However, the **Demographics** class appears loosely defined and may benefit from being integrated with either the **Poll** or **User** classes to better collect and analyze data.

---

### Suggested Changes
- **Add a clear link between Poll and Demographics**: Integrating Demographics into the Poll class can help capture demographic data as part of user responses, making the design more cohesive and functional.