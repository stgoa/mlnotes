# ML System Design Interviews: A Step-by-Step Guide

## Step 1: Business Problem Definition
- What does success look like?
- How do we quantify the business goal?
- Find proxies for business metric, better defined, easier to model.
- Define label and training examples precisely.
- How long is the way to determine if an impression is a click?
- Does the proxy event have a reasonable time period? (determines iteration speed)
- Is the event of interest sparse?
- Do features contain info about the event?
- Do we care more about precision or recall?
- What data slice do we care more about getting right?

## Step 2: Data
- Describe data model.
- Identify batch and streaming data.
- Determine if real-time training is needed.
- Decide between real-time and batch training (monitor accuracy degradation over time).
- Handle static features and retrieve batch.
- Implement real-time joins.
- Consider sampling training data (importance sampling, reservoir sampling).

## Step 3: Evaluation
### Offline Evaluation (Fast and Efficient):
- Compute baseline model metric (heuristic, business, constant/random model).
- Use 3 splits model (train/test/validate) over time.
- Choose an interpretable metric.
- Perform prediction analysis (calibration).
- Metrics over slices to understand performance sources.

### Online Evaluation (After Finding Candidate):
- Implement more accurate online evaluation.

## Step 4: Features
- Monitor features over time.
- Address issues like leakage and coverage.

## Step 5: Model
- Be systematic.
- Implement versioning and tracking.
- Choose the ML task best suited for the problem.
- Prioritize simplicity over complexity.
- Avoid premature optimization.

## Step 6: Experimentation
- Minimize time to the first experiment.
- Use an identity transform for engineering effects (A/A test) as a sanity check.
- Replace the "identity transform" with a simple modifier for A/B testing.
- Implement random A/B tests.
- Look for offline/online gaps.
- Always include kill switches in the code.
- Check for calibration (sum y_hat / sum y) in random A/B tests.

## Step 7: Scalability and Infrastructure
- Consider scalability for data volume, feature dimensions, and model complexity.
- Design a scalable and efficient infrastructure.
- Discuss distributed computing, parallelization, and resource allocation.

## Step 8: Deployment and Monitoring
- Outline deployment strategy.
- Discuss containerization, orchestration, and rollback strategies.
- Implement robust monitoring for model performance and system health.
- Set up alerts for anomalies and degradation.

## Step 9: Continuous Integration and Continuous Deployment (CI/CD)
- Discuss CI/CD pipeline for automating testing, model deployment, and rollback processes.
- Consider versioning for models, data, and code.
- Manage backward compatibility and updates.

## Step 10: Ethical Considerations
- Address ethical concerns related to data, biases, and impact on different user groups.
- Mitigate biases and ensure fairness in the ML system.

## Step 11: Security
- Implement security measures for protecting sensitive data.
- Discuss encryption, access controls, and security best practices.
- Consider strategies for defending against adversarial attacks.

## Step 12: Model Explainability and Interpretability
- Discuss model interpretability.
- Ensure stakeholders can understand and trust model decisions.
- Consider techniques for model explainability.

## Step 13: Feedback Loops and Model Maintenance
- Design feedback loops for continuous model improvement.
- Gather user feedback and update the model accordingly.
- Implement strategies for model maintenance, including retraining schedules and versioning.

