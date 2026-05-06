# Literature Review

Approaches or solutions that have been tried before on similar projects.

**Summary of Each Work**:

- **Source 1**: [The Hanabi Challenge: A New Frontier for AI Research (Bard et al., 2019)]

  - **[Link](https://arxiv.org/abs/1902.00506)**
  - **Objective**: To propose Hanabi as a primary benchmark for AI research, focusing on multi-agent cooperation and theory of mind.
  - **Methods**: The researchers developed a framework for representing the game state as a numerical vector (state featurization). They established standard evaluation metrics for performance.
  - **Outcomes**: Proved that traditional "self-play" algorithms (which work for Chess e.g.) fail in Hanabi because the game requires understanding the "intent" of other players.
  - **Relation to the Project**: This work provides the technical blueprint for the project. It defines the "State Representation" that will serve as the input variables for the regression model(s).

- **Source 2**: [The Hidden Rules of Hanabi: How Humans Outperform AI Agents (CHI 2023)]

  - **[Link](https://dl.acm.org/doi/full/10.1145/3544548.3581550)**
  - **Objective**: To investigate why high-level human players consistently outperform state-of-the-art AI agents by identifying "hidden" coordination strategies.
  - **Methods**: A combination of quanitative gameplay analysis and qualitative player studies to identify "conventions" (unwritten rules that humans use to convey complex information with simple hints).
  - **Outcomes**: Identified that human success is driven by "pragmatic" communication (e.g. a hint isn't just about a color, it's an instruction to play or discard).
  - **Relation to the Project**: This source justifies the *Feature Importance* aspect of the project. It suggests that the model should find high importance in "contextual features" (e.g. the position of card of timing of hint). It provides a theoretical framework to explain why certain features are identified as success drivers by the ML model.

- **Source 3**: [Predictive Analysis of NBA Game Outcomes through Machine Learning (Various authors)]

  - **[Link](https://dl.acm.org/doi/fullHtml/10.1145/3635638.3635646)**
  - **Objective**: To accurately predict the final score or the winner of a game by analyzing historicl performance data and real-time in-game statistics. Additionally, to determine which key performance indicators (KPIs) have the most significant impact on the final score (feature importance).
  - **Methods**: Researchers used following ML algorithms: Logistic Regression, Support Vector Machines, Long Short-Term Memory and Random Forest. The performed extensive Feature Engineering by converting raw game events into structured variables. They then used Feature Importance techniques to rank these based on their predictive power. 
  - **Outcomes**: Study successfully demonstrated that non-lineral models like Random Forest can predict game results with high accuracy.
  - **Relation to the Project**: Finally, the methodological blueprint. We try to adopt the same core methodology: converting sequential "play-by-play" logs into a structured dataset to predict a continuous final score via Random Forest Regression. The NBA project demonstrates how ensemble models can effectively map specific in-game actions to a final point total which is exactly how we quantify which cooperative moves in Hanabi lead to a perfect 25-point result.
