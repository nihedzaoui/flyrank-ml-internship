# Final Retrospective

## A note to my Week 1 self

At the beginning of the FlyRank ML track, I approached the project mainly as a machine-learning problem: understand the available search data, identify useful signals, train a model, and use its predictions to support content decisions. My initial instinct was to focus on the model itself and on whether it could produce useful predictive performance. By the end of the project, my understanding had changed significantly. I learned that building a useful ML system is much more than training a model: the quality of the data, the definition of the target, the validation strategy, and the way predictions are translated into decisions can matter just as much as the algorithm.

One of the biggest changes in my approach was learning to treat the data and problem definition as first-class parts of the ML system. I worked on a data contract to make the expected inputs, fields, assumptions, and constraints explicit. I also performed a feature leakage check before relying on candidate signals. This changed the way I think about modeling. Instead of immediately asking, “Which model should I use?”, I now ask, “Is this the right problem formulation, is the data trustworthy, and would this signal actually be available when the decision is made?”

The validation stage reinforced this lesson. During the validation audit, I encountered issues that required investigation rather than simply accepting the first evaluation results. This made the difference between a model that produces a metric and a model whose results can actually be trusted much clearer to me. I learned to inspect the evaluation process itself, document assumptions, and treat unexpected results as evidence that needs investigation.

Another important change was moving from predictions to actions. The project eventually became more than a modeling exercise. The content-refresh analysis and action playbook translated model and search signals into recommendations that could be prioritized. The final ranked refresh queue was designed to make those recommendations easier to inspect and act upon. This taught me that an ML project's value is often determined by the decision it enables, not simply by the sophistication of the model behind it.

If I continued the project, I would build a stronger production-oriented version of the system. I would improve the data pipeline, introduce more systematic monitoring of data and model drift, expand the validation dataset, and evaluate the recommendations over time using real outcomes. I would also investigate how to incorporate additional contextual signals while maintaining a clear data contract and avoiding leakage. The goal would be to move from a validated prototype toward a continuously evaluated decision-support system.

### The three most transferable lessons

**1. Validate the problem before optimizing the model.**  
A strong algorithm cannot compensate for a poorly defined target, unreliable data, or leakage. Data contracts, feature audits, and validation design should come before model optimization.

**2. Evaluation is part of engineering, not just a final number.**  
A metric is only meaningful when I understand how it was produced. Reproducibility, validation assumptions, data quality, and failure analysis are essential for deciding whether a result deserves to be trusted.

**3. Turn technical outputs into decisions.**  
A model becomes more useful when its outputs can be understood and acted upon. Designing the refresh scoring, recommendation logic, and ranked queue pushed me to think about the person using the system rather than only the model producing the prediction.

Most importantly, the project changed how I work with AI. I used AI tools as development and thinking partners for coding, debugging, brainstorming, and documentation, but I learned that the responsibility for the final result remains mine. I had to inspect outputs, test implementations, investigate unexpected behavior, and make the final technical decisions. That combination—using AI to accelerate exploration while maintaining human verification—is a working habit I will carry into future research and engineering projects.

Looking back at Week 1, I would tell myself: **do not start with the model. Start with the decision, the data, and the evidence you will need to trust the result.**
