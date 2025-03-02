---
layout: model
title: Pipeline to Detect Radiology Related Concepts
author: John Snow Labs
name: ner_radiology_wip_clinical_pipeline
date: 2022-03-21
tags: [licensed, ner, clinical, en]
task: Named Entity Recognition
language: en
nav_key: models
edition: Healthcare NLP 3.4.1
spark_version: 3.0
supported: true
annotator: PipelineModel
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---


## Description


This pretrained pipeline is built on the top of [ner_radiology_wip_clinical](https://nlp.johnsnowlabs.com/2021/04/01/ner_radiology_wip_clinical_en.html) model.


{:.btn-box}
[Live Demo](https://demo.johnsnowlabs.com/healthcare/NER_RADIOLOGY/){:.button.button-orange.button-orange-trans.arr.button-icon}
[Open in Colab](https://colab.research.google.com/github/JohnSnowLabs/spark-nlp-workshop/blob/master/tutorials/streamlit_notebooks/healthcare/NER_RADIOLOGY.ipynb){:.button.button-orange.button-orange-trans.arr.button-icon}
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/clinical/models/ner_radiology_wip_clinical_pipeline_en_3.4.1_3.0_1647874482693.zip){:.button.button-orange.button-orange-trans.arr.button-icon.hidden}
[Copy S3 URI](s3://auxdata.johnsnowlabs.com/clinical/models/ner_radiology_wip_clinical_pipeline_en_3.4.1_3.0_1647874482693.zip){:.button.button-orange.button-orange-trans.button-icon.button-copy-s3}


## How to use






<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}

```python
from sparknlp.pretrained import PretrainedPipeline

pipeline = PretrainedPipeline("ner_radiology_wip_clinical_pipeline", "en", "clinical/models")


pipeline.fullAnnotate("Bilateral breast ultrasound was subsequently performed, which demonstrated an ovoid mass measuring approximately 0.5 x 0.5 x 0.4 cm in diameter located within the anteromedial aspect of the left shoulder. This mass demonstrates isoechoic echotexture to the adjacent muscle, with no evidence of internal color flow. This may represent benign fibrous tissue or a lipoma.")
```
```scala
import com.johnsnowlabs.nlp.pretrained.PretrainedPipeline

val pipeline = new PretrainedPipeline("ner_radiology_wip_clinical_pipeline", "en", "clinical/models")


pipeline.fullAnnotate("Bilateral breast ultrasound was subsequently performed, which demonstrated an ovoid mass measuring approximately 0.5 x 0.5 x 0.4 cm in diameter located within the anteromedial aspect of the left shoulder. This mass demonstrates isoechoic echotexture to the adjacent muscle, with no evidence of internal color flow. This may represent benign fibrous tissue or a lipoma.")
```
</div>


## Results


```bash
+---------------------+-------------------------+
|chunks               |entities                 |
+---------------------+-------------------------+
|Bilateral            |Direction                |
|breast               |BodyPart                 |
|ultrasound           |ImagingTest              |
|ovoid mass           |ImagingFindings          |
|0.5 x 0.5 x 0.4      |Measurements             |
|cm                   |Units                    |
|anteromedial aspect  |BodyPart                 |
|left                 |Direction                |
|shoulder             |BodyPart                 |
|mass                 |ImagingFindings          |
|isoechoic echotexture|ImagingFindings          |
|muscle               |BodyPart                 |
|internal color flow  |ImagingFindings          |
|benign fibrous tissue|ImagingFindings          |
|lipoma               |Disease_Syndrome_Disorder|
+---------------------+-------------------------+
```


{:.model-param}
## Model Information


{:.table-model}
|---|---|
|Model Name:|ner_radiology_wip_clinical_pipeline|
|Type:|pipeline|
|Compatibility:|Healthcare NLP 3.4.1+|
|License:|Licensed|
|Edition:|Official|
|Language:|en|
|Size:|1.7 GB|


## Included Models


- DocumentAssembler
- SentenceDetectorDLModel
- TokenizerModel
- WordEmbeddingsModel
- MedicalNerModel
- NerConverter
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMDM4NjA2MywzMDc2OTc3MSwtMTI3Nj
QxNzgwMl19
-->