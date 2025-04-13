
# NEET Question Paper Analysis and Generator

## Introduction
This project focuses on both generating and evaluating multiple-choice questions (MCQs) in the context of NEET (National Eligibility cum Entrance Test) preparation. In addition to generation, the system also supports evaluating existing NEET-style questions by retrieving relevant textbook content and assessing their difficulty or alignment. This dual approach allows the system to assist in both creating new questions and validating the quality of existing ones, making it useful for educators, students, and content developers.


## Demo

Please watch this 7 minutes video for a better understanding

https://youtu.be/Enh8vcAN3gg


## Installation and Deployment

Clone the repository
```bash
  git clone https://github.com/Roasted12/NEET-Question-Analysis
```
and download these 2 files as well (Github does not support files larger than 50MB to be uploaded)

Link: https://drive.google.com/drive/folders/1GIsy1hsQeiOPpF7M80LSXHwJsbwREgpy?usp=sharing

The file structure should be like

```bash
.
├── .ipynb_checkpoints/             # Auto-generated Jupyter checkpoints
├── gpt2-physics/                   # GPT-2 fine-tuned model folder
├── static/                         # Optional output or asset directory
├── 2017.xlsx                       # Annotated NEET
├── 2023.xlsx                       # Annotated NEET
├── Evaluation_loglike.ipynb        # Notebook for GPT-2 log-likelihood scoring
├── imlbook.pdf                     # Main textbook source used for IML MCQ generation
├── IMLPROJECT.ipynb                # Main notebook with training, testing, evaluation
├── imltest1.json                   # USMLE Questions
├── imltest2.json                   # Chinese Entrance Exam
├── neet_predictions_with_gemini.xlsx  # Output predictions with Gemini difficulty scores
├── requirements.txt                # List of all required Python packages
```

Ensure you have Python 3.12 installed

Install the requirements file

```bash
  pip install -r requirements
```

## Choosing the Notebook

There are 2 notebooks

1)IMLProject.ipynb

2)Evaluation_loglike.ipynb

## Explanation
IMLProject.ipynb contains the main Gemini 2.0 flash model, its testing on various datasets, including UCLE and Chinese, and finally the main goal of this project, NEET questions evaluation, in this case we took the 2023 paper.
The last few cells of this notebook contains the question generation of the subject "Machine Learning" as part of the feedback receieved in the mid-review of the project as well as NEET Questions Generation.

Evaluation_loglike.ipynb is the notebook which contains GPT-2, a publicly available transformer which we have used to evaluate generated questions as Gemini does not support open tokens evalutaion as per its documentation. The folder gpt2-physics contains the trained GPT-2 model. The notebook has evaluation part which also of both Gemini and GPT-2,
as said earlier, we cannot access evaluation of Gemini as written in its API documentation so what we have done is generate the question from Gemini and then evaluate its generation with the help of GPT-2' Log-Liklihood.


## Deployment

You may run the IMLProject.ipynb locally and check out what has been done.

The Evaluation_loglike.ipynb was done on Google Collab as we had dependencies issues with the python "torch" module.

We have explained each cell in the ipynb notebook as well.
