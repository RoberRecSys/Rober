Thanks for your insightful comments. We try to alleviate your concern one by one.

**R1**: <1>In explainable recommendation, robustness ensures that explanations for similar user-item pairs do not vary too much. It reflects the system's ability to maintain performance and reliability under various conditions, such as noisy inputs and data perturbations, which is crucial in recommendation scenarios like finance and healthcare. <2>Research in machine learning indicates that improving model robustness has minimal impact on prediction accuracy. Instead, it can enhance the model's generalization and stability on unknown samples. This is also verified in Table 2 results.

**R2**: Thanks for your suggestions. This paper is organized progressively, beginning with the preliminaries, then presenting basic robustness goals, and finally discussing complex reinforcement learning methods. This structure minimizes cognitive difficulties for readers, particularly those unfamiliar with this field. We'll refine the paper's structure in the final version following your suggestions.

**R3**:TF-IDF is a simple, quick method for calculating token importance (characteristic 1) and semantic similarity is corresponding to synonmy exploration (characteristic 2) and they don't conflict. As mentioned in Section 3.4 (Line 359~366), the two characteristics improve the effectiveness of adversarial learning from different perspectives,  serving for data understanding and data augmentation, respectively. The ablation results in Table 3 show that the two objectives are complementary.

**R4**: Thanks for your suggestions. Our method for modeling token semantics is a fine-grained approach at token level, aiming to align hierarchically with the first objective of calculating token importance. Your suggestion of high-level modeling is inspiring. I think combining both approaches can achieve multi-level semantic modeling. We will further refine our method following that.

**R5**: **Motivation**: <1>The two tasks, importance estimation and synonyms exploration, involve sequential decision-making, it is crucial to model the cumulative effectiveness of decisions. RL is naturally suited for this type of problem. <2>As illustrated in line 378\~387, the two tasks can influence each other and jointly determine the quality of adversarial training. A common optimization objective is necessary to establish collaboration. Thus we design the dual-policy RL method. **Details**: We use the REINFORCE method to update parameters. When estimating token importance, the action space is continuous (0\~1). Following prior works, we transform to estimate the mean and variance of token importance distribution. While, the space for synonym exploration is discrete (the given vocabulary), which can use standard sampling. And we limit the exploring space by requiring synonym similarity to exceed a threshold and use a baseline on reward function for training stability.

**R6**: <1>We use F1 score, Recall, and Precision of BERTScore for a comprehensive semantic evaluation. BLEU and ROUGE are also included as they are common in text generation research. Unlike RecSys ranking metrics, text similarity metrics, especially BERTScore, are relatively stable, so minor changes can indicate performance improvement. We evaluate robustness of text generation tasks following the pattern from traditional classification tasks in Figure 3, and Table 2 also shows enhanced robustness benefits model generalization. <2>We directly use well-prepared datasets commonly used in prior works (NETE, PETER, CER, ...) for experiments, repeating the split process five times and reporting average performance on the testing set to meet cross-validation requirements.

**R7**: We have analysed the reasons about the results on MAE at Line 734~741. Moreover, we add the following analyses: <1>The results in Table 2 show that, on rating prediction task, our final Rober method outperforms the original model in more than half of the cases (5/9), and it is comparable in the remaining cases (4/9), with minor decreases. <2>In the setting of explainable recommendation, explanation generation task is the most critical, while rating prediction is auxilliary. Existing works [1, 2, 3, 4, 5] also only verified that their rating prediction performance is comparable to the baselines, and some even didn't show the performance of rating prediction.

[1] Generate Neural Template Explanations for Recommendation(CIKM '20)

[2] Personalized Transformer for Explainable Recommendation(ACL '21)

[3] Personalized Prompt Learning for Explainable Recommendation(TOIS '22)

[4] The Problem of Coherence in Natural Language Explanations of Recommendations(ECAI '23)

[5] UCEpic: Unifying Aspect Planning and Lexical Constraints for Generating Explanations in Recommendation(KDD '23)

**R8**: The ablation study in Table 3 verify the significant role of the two characteristics in the robustness of generating explanations. They are complementary and both matter: assigning different importance weights to tokens helps emphasize the main points of the sentence, while replacements with synonyms enhances the expressiveness of the models. Moreover, unlike RecSys ranking metrics, text similarity metrics, especially BERTScore, are relatively stable, so minor changes can indicate performance improvement.

**R9**: Thanks for your suggestions. We'll definitely check that in the final version.

**Response to Q1**: Please refer to R7.

**Response to Q2**: Please refer to R8.

Thanks again for your comments and we hope the above analyses can alleviate your concerns.