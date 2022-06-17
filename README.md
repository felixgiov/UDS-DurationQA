Dataset from the paper "Improving Event Duration Question Answering by Leveraging Existing Temporal Information Extraction Data"
------

### Introduction
Understanding event duration is essential for understanding natural language. However, the amount of training data for tasks like duration question answering, i.e., McTACO, is very limited, suggesting a need for external duration information to improve this task. The duration information can be obtained from existing temporal information extraction tasks, such as UDS-T and TimeBank, where more duration data is available. A straightforward two-stage fine-tuning approach might be less likely to
succeed given the discrepancy between the target duration question answering task and the intermediary duration classification task. This paper resolves this discrepancy by automatically recasting an existing event duration classification task from UDS-T to a question answering task similar to the target McTACO. We investigate the transferability of duration information by comparing whether the original UDS-T duration classification or the recast UDS-T duration question answering can be
transferred to the target task. Our proposed model achieves a 13% Exact Match score improvement over the baseline on the McTACO duration question answering task, showing that the two-stage fine-tuning approach succeeds when the discrepancy between the target and intermediary tasks are resolved.

### Overview of the dataset
We recast our data from the [UDS-T dataset](http://decomp.io/projects/time/).
We provide the train/dev/test split as specified in the paper under `data/`.
In each file, there are lines of tab-separated data, each line representing an instance of a question-answer pair.
Each line contains the following information:

`sentence \t  question \t  answer \t label`

 * **sentence**: a context sentence where the question is based on.
 * **question**: a question asking about the duration of an event in the sentence.
 * **answer**: a potential answer to the question.
 * **label**: whether the answer is a plausible answer. "yes" indicates the answer is plausible, "no" otherwise.

### Citation
If you use this dataset, please cite our paper ["Felix Giovanni Virgo, Fei Cheng, Sadao Kurohashi. Improving Event Duration Question Answering by Leveraging Existing Temporal Information Extraction Data. Proceedings of the 13th International Conference on Language Resources and Evaluation (LREC), (2022)"](http://www.lrec-conf.org/proceedings/lrec2022/pdf/2022.lrec-1.473.pdf)

Bibtex for citations:

```bibtex
@InProceedings{virgo-cheng-kurohashi:2022:LREC,
  author    = {Virgo, Felix  and  Cheng, Fei  and  Kurohashi, Sadao},
  title     = {Improving Event Duration Question Answering by Leveraging Existing Temporal Information Extraction Data},
  booktitle      = {Proceedings of the Language Resources and Evaluation Conference},
  month          = {June},
  year           = {2022},
  address        = {Marseille, France},
  publisher      = {European Language Resources Association},
  pages     = {4451--4457},
  abstract  = {Understanding event duration is essential for understanding natural language. However, the amount of training data for tasks like duration question answering, i.e., McTACO, is very limited, suggesting a need for external duration information to improve this task. The duration information can be obtained from existing temporal information extraction tasks, such as UDS-T and TimeBank, where more duration data is available. A straightforward two-stage fine-tuning approach might be less likely to succeed given the discrepancy between the target duration question answering task and the intermediary duration classification task. This paper resolves this discrepancy by automatically recasting an existing event duration classification task from UDS-T to a question answering task similar to the target McTACO. We investigate the transferability of duration information by comparing whether the original UDS-T duration classification or the recast UDS-T duration question answering can be transferred to the target task. Our proposed model achieves a 13\% Exact Match score improvement over the baseline on the McTACO duration question answering task, showing that the two-stage fine-tuning approach succeeds when the discrepancy between the target and intermediary tasks are resolved.},
  url       = {https://aclanthology.org/2022.lrec-1.473}
}
```
