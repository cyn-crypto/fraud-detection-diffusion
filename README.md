**Problem Statement & Motivation**

Fraud detection systems are commonly designed to assign scalar anomaly scores to transactions, enabling automated
identification of potentially fraudulent activity. While effective in practice, these approaches often provide limited
interpretability, offering little insight into why a transaction is flagged as anomalous. This lack of transparency can
hinder trust, complicate auditing processes, and make it difficult for analysts to act on model outputs in high-stakes
financial environments. In many real-world deployments, the ability to justify and explain predictions is as
important as the predictions themselves. In addition, many traditional fraud detection approaches rely on supervised
learning techniques that require labeled fraudulent data. However, fraud is inherently rare, continuously evolving,
and often underrepresented in available datasets, making it difficult to obtain comprehensive and up-to-date labels.
Consequently, supervised models may struggle to generalize to emerging fraud patterns or previously unseen attack
strategies.This limitation has motivated the use of unsupervised and one-class learning methods that model normal
behavior and identify deviations from it.

In this project, we explore an unsupervised generative modeling approach based on diffusion models trained exclusively
on legitimate transactions. Diffusion models have recently demonstrated strong performance in learning complex data
distributions through an iterative denoising process, gradually transforming noise into samples that follow the training
distribution. By learning the manifold of normal transactions, deviations from this learned distribution could be
used as indicators of anomalous behavior without requiring labeled fraud examples. Beyond standard reconstructionbased
signals, this work is motivated by the hypothesis that the internal dynamics of the diffusion process - specifically,
the denoising trajectories which may encode additional structure that could support interpretability. In particular,
the sequence of intermediate states generated during reverse diffusion may reflect how a transaction evolves toward
the learned data manifold, potentially revealing differences between normal and anomalous samples. Prior work
on score-based generative modeling suggests that such trajectories are closely tied to the geometry of the learned
data distribution. The motivation behind this approach is twofold. First, we aim to improve fraud detection in
settings where labeled data is scarce or unreliable by leveraging only normal transaction data. Second, we seek to
investigate whether diffusion-based trajectory representations can provide interpretable signals that explain why a
transaction deviates from normal behavior. Rather than assuming that trajectory geometry will necessarily yield
improved explainability, this project empirically evaluates whether such trajectory-based features offer meaningful
advantages over standard reconstruction-based anomaly signals.

The Report can be found in this same folder which contains the Methodology, Results and everything else.
