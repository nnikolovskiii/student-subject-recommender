# student-subject-recommender
Recommender system for students for their elective courses.

A graph neural network that suggests elective courses to FINKI students (February 2024).

- **Data:** students, professors, courses and subjects from FINKI timetable and enrolment data (2018 onward) form one
  heterogeneous graph with about 147,000 relations (student attended course, professor instructed
  course, course covers subject). Each subject gets a 384-number text embedding plus its level and
  semester type as features.
- **Model:** two GAT layers (PyTorch Geometric) learn node embeddings; training is link prediction on
  the "attended an elective" edges, with the other edges used only for message passing, and
  negative sampling for edges that do not exist.
- **Result:** ROC AUC **0.885** on held-out test edges. With 2× to 6× as many negative samples it
  stays between 0.883 and 0.885 (average 0.884).
- **Where:** `data_fetching/` → `data_preprocessing/` → `model/Student_subject_link_prediction.ipynb`
  (Colab notebooks).

![image](https://github.com/nnikolovskiii/student-subject-recommender/assets/86115698/6361aeb3-e83b-426f-ab64-4511aa409639)

![Finki students - Frame2](https://github.com/nnikolovskiii/student-subject-recommender/assets/86115698/fe8fc64d-9656-4777-8a53-851ce610b0d7)


![idYC5f2L1X (1)](https://github.com/nnikolovskiii/student-subject-recommender/assets/86115698/f70c4ea0-02a4-4bce-a7f9-27d295ae5730)
[Miro board](https://miro.com/app/board/uXjVN53qblY=/?share_link_id=125372733190)
