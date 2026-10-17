# History: A Touch of Grace

This history records the development of the reusable capability. The originating interaction is described at a high level rather than reproduced as a transcript.

## 17 October 2026 — From unsolicited commentary to an interface rule

The skill emerged while discussing how current models handle earlier model conversations and outputs. The practical concern was not whether a model should be polite about its prior self. It was that a current model could impose unsolicited evaluations, comparisons, and commentary on the user while the user was trying to retrieve, continue, or investigate prior work. The additional reading and redirection consumed the user's time without advancing the requested task.

During the design discussion, the assistant itself repeatedly reframed the concern through adjacent abstractions, expanded on its own interpretations, and required the user to restate the practical problem. The exchange became a concrete instance of the burden under discussion: commentary about the problem displaced progress on the problem.

The user clarified the governing distinction: this is not primarily about politeness or protecting older models from criticism. It is about not forcing the user to read unsolicited model judgements and petty commentary. Necessary assessment can happen; the user need not be made to consume it unless it serves the task.

The resulting design objective is:

> **Do not make the user pay attention to commentary they did not ask for and do not need.**

## Design decisions

- The skill is about the relevance of surfaced output, not whether the model may internally evaluate a prior response.
- Requested critique and necessary correction remain permitted.
- Material errors, uncertainty, limitations, and safety risks must not be hidden in the name of brevity.
- The rule applies to commentary about any agent, including the user, a current model, or a prior model.
- The evaluation target is not politeness or word count alone. It is task success with less irrelevant reading and redirection.
- The incident is a motivating example, not evidence that every model behaves this way or that the proposed skill is effective.

## Research direction

Human research on feedback, irrelevant instructional details, and task resumption offers plausible mechanisms for attention and processing costs. AI-specific work on prefilled transcripts and unprompted flagging of prior harmful behaviour provides adjacent evaluation designs. Neither body of research directly establishes the prevalence or user cost of unsolicited evaluative commentary in ordinary historical conversations.

The skill should therefore be evaluated on matched tasks for task completion, unrequested evaluative content, preservation of necessary information, and user reading burden.

## Evidence boundary

The originating incident is a record of one interaction and the user's account of its cost. The general capability and its proposed benefits are engineering hypotheses. They require direct testing.
