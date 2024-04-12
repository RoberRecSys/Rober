**Highlights:**
- New base model: **CER** (The Problem of Coherence in Natural Language Explanations of Recommendations, ECAI '23)
- New dataset from fashion domain: Amazon-ClothingShoesAndJewelry (**AZ-CSJ**)

|          Metrics          |   BLEU-1   | BLEU-4 | ROUGE-1 | ROUGE-2 |BS-F1 |BS-Recall|BS-Precision| MAE (&darr;) |
|:-------------------------:|:----------:|:------:|:-------:|:-------:|:----------:|:---------:|:---------:|:-------:|
| Dataset | AZ-CSJ (**New!**) |        |         |         |            |           |           |         |
|            CER            |   21.588   | 3.595  | 29.843  |  8.496  |   88.884   |  87.873   |  89.973   | 0.833   |
|         CER-Rober         |   **21.760**   | **4.108**  | **30.144**  |  **8.727**  |   **89.111**   |  **88.165**   |  **90.127**   | **0.830**   |
|       Dataset       | YELP |        |         |         |            |           |           |         |
|            CER            |   16.824   | 2.491  | 25.506  |  6.879  |   87.836   |  86.793   |  88.971   | 0.807   |
|         CER-Rober         |   **18.885**   | **2.775**  | **26.814**  |  **7.056**  |   **88.188**   |  **87.141**   |  **89.322**   | **0.801**   |
|       Dataset       | TA-HK |        |         |         |            |           |           |         |
|            CER            |   24.874   | 3.987  | 29.425  |  8.373  |   88.387   |  87.622   |  89.211   | 0.667   |
|         CER-Rober         |   **24.954**   | **4.156**  | **29.757**  |  **8.467**  |   **88.766**   |  **87.895**   |  **89.698**   | **0.649**   |
|       Dataset       | AZ-MT |        |         |         |            |           |           |         |
|            CER            |   17.186   | 2.273  | 24.123  |  5.815  |   86.785   |  85.722   |  87.958   | 0.749   |
|         CER-Rober         | **17.429** | **2.511**  | **25.436**  |  **6.427**  |  **87.125**  |  **85.857**   |  **88.511**   | **0.742**   |

- Notes: "BS" represents "BERTScore". Bold font indicates the best performance. "&darr;" means that a lower value indicates better performance. 
