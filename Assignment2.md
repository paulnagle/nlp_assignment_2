MSc in Artificial Intelligence Natural Language Processing Module
>
> **ASSIGNMENT** **2**
>
> **Low-Resource** **Speech-to-Text** **Translation:** **Building**
> **an** **Irish→English** **Cascaded** **Pipeline**

Module Weighting: 50% of total module mark 

Submission Deadline: 10th May 2026, 23:59

Format: ACL-style conference paper + code submission Dataset: IWSLT 2026

Irish–English Speech Translation Data Mode: Individual submission



> Students are expected to work independently. All submissions will be
> checked for academic integrity.

NLP Module — Assignment 2: Irish→English Speech Translation

**1.** **Overview**

This assignment forms the second and major piece of assessed coursework
for the Natural Language Processing module. It is worth 50% of your
overall module grade. You will design, implement, and evaluate a
cascaded speech-to-text translation system for the Irish–English
language pair, using publicly available pretrained models and the IWSLT
2026 shared task dataset.

You are not required to train large neural models from scratch. Instead,
you are expected to make informed choices among available pretrained
components, integrate them into a coherent pipeline, rigorously
evaluatetheresults, and writeup your findings in thestyleofan academic
conferencepaper using the ACL template.

**2.** **Background** **and** **Motivation**

**2.1** **Low-Resource** **Speech** **Translation**

Speech translation (ST) — the task of converting spoken audio in one
language into text in another — is challenging even for well-resourced
language pairs. For low-resource languages, the challenge is compounded
by limited transcribed audio data, fewer high-quality pretrained models,
and greater linguistic diversity. Irish (Gaeilge) is one such language:
a living minority language with active speaker communities but
comparatively little digital data compared to languages such as French
or Mandarin.

This assignment asks you to tackle a real, contemporary shared task:
IWSLT 2026 Track 1 (Low-Resource Speech-to-Text Translation). Rather
than competing in the full shared task, you will engage with the same
data and evaluation framework but within the scope of an MSc research
exercise.

**2.2** **Why** **Cascaded** **ASR→MT?**

There are two broad architectural strategies for speech translation:
end-to-end systems (which jointly model speech and translation) and
cascaded systems (which chain a separate Automatic Speech Recognition
(ASR) module with a Machine Translation (MT) module). Cascaded systems
have several practical advantages in low-resource settings:

> • ASR and MT components can be independently pretrained on large
> datasets in their respective domains.
>
> • Errors can be diagnosed and improved at each stage independently.
>
> • Strong off-the-shelf models (e.g. Whisper for ASR, NLLB for MT) are
> readily available.

This assignment focuses on the cascaded approach, requiring you to make
principled decisions about each component.

**3.** **Learning** **Outcomes**

On successful completion of this assignment, you will be able to:

**Technical** **Skills**

> • Load and preprocess real-world speech data in a low-resource NLP
> setting.
>
> • Deploy and integrate pretrained ASR and MT models using the Hugging
> Face ecosystem. • Build a functioning end-to-end cascaded speech
> translation pipeline.
>
> • Apply standard evaluation metrics (BLEU, chrF++) correctly to ST
> outputs.

Deadline: 10 May 2026 \| Page 2

NLP Module — Assignment 2: Irish→English Speech Translation

**Experimental** **and** **Analytical** **Skills**

> • Design a principled comparison between a baseline and an improved
> system. • Perform error analysis to identify and classify failure
> modes.
>
> • Interpret evaluation results in the context of low-resource NLP
> challenges.

**Academic** **Communication**

> • Write a research paper following ACL conference-paper conventions.
>
> • Communicate technical decisions and experimental findings clearly
> and critically.

**4.** **Assignment** **Task**

You must complete all of the following components:

**4.1** **Data** **Preparation**

> • Clone and explore the IWSLT 2026 Irish–English dataset from GitHub
> [(<u>https://github.com/acl-org/acl-style-files)</u>](https://github.com/acl-org/acl-style-files)
>
> • Understand its structure: audio files, transcriptions, and reference
> translations. • Apply any necessary audio preprocessing (resampling,
> format normalisation).
>
> • Document dataset statistics: number of utterances, total duration,
> split sizes.

**4.2** **Baseline** **Cascaded** **Pipeline**

> • Select a pretrained ASR model suitable for Irish speech (e.g. a
> Whisper variant).
>
> • Select a pretrained MT model capable of Irish→English translation
> (e.g. NLLB-200). • Integrate the two components into a sequential
> pipeline.
>
> • Run inference on the test or development set and save outputs.

**4.3** **Improved** **System**

> • Design and implement at least one meaningful improvement over the
> baseline.
>
> • Possible directions include: a different ASR front-end,
> Irish-specific ASR fine-tuning, different MT model, beam search
> tuning, output post-processing, or language-model rescoring.
>
> • Clearly document what you changed and why.

**4.4** **Evaluation**

> • Compute BLEU and chrF++ scores for both systems. • Report results in
> a clearly formatted table.
>
> • Optionally compute COMET scores if compute budget allows.

**4.5** **Error** **Analysis**

> • Analyse at least 20 system outputs qualitatively.
>
> • Identify and categorise error types (e.g. ASR substitutions,
> deletion/insertion, MT mistranslations, hallucinations).
>
> • Discuss which errors are most common and their likely causes.

**5.** **Technical** **Requirements**

Deadline: 10 May 2026 \| Page 3

NLP Module — Assignment 2: Irish→English Speech Translation

**5.1** **Permitted** **Models** **and** **Tools**

You are encouraged to use any of the following pretrained model
families, but you are not limited to them:

> • **Whisper** **(openai/whisper-\*),** **Wav2Vec2,** **or**
> **Irish-specific** **ASR** **models** **from** **Hugging** **Face.** •
> **NLLB-200** **(facebook/nllb-200-\*),** **Helsinki-NLP** **Opus-MT,**
> **or** **mBART-50.**
>
> • **Hugging** **Face** **transformers,** **datasets,** **evaluate,**
> **jiwer,** **sacrebleu.**

You must document every external model used, including its Hugging Face
model ID or source URL, licence, and the reason for choosing it.

**5.2** **Compute** **Constraints**

All experiments can be runnable on Google Colab (free tier or Colab Pro)
or a standard laptop with a GPU (or CPU with patience). You will not
require access to multi-GPU clusters. Specifically:

> • Do not train large models from scratch (e.g. no training of full
> Whisper or NLLB-200 weights). • Fine-tuning lightweight adapters or
> LoRA layers on small subsets is permitted, but is not
>
> required.
>
> • If your experiments required paid compute, state this clearly in
> your report and ensure your code can produce representative results
> within Colab free-tier constraints on a subset.

**6.** **Deliverables**

You must submit all of the following via the module submission portal:

||
||
||
||
||
||
||
||
||
||
||

Your code must be reproducible. Include all random seeds and version
information. A marker should be able to clone your notebook and
reproduce your headline results.

**7.** **Report** **Guidelines**

**7.1** **Format**

Your report must use the ACL 2025 LaTeX or Word template. The template
is available at:
[<u>https://github.com/acl-org/acl-style-files</u>](https://github.com/acl-org/acl-style-files)

Recommended length: 6–8 pages (excluding references and appendices).
Appendices may include additional tables, error examples, and your AI
use declaration.

Deadline: 10 May 2026 \| Page 4

NLP Module — Assignment 2: Irish→English Speech Translation

**7.2** **Recommended** **Structure**

> • **Abstract** **(150–200** **words):** **What** **you** **did,**
> **how,** **and** **your** **key** **result.** • **Motivation,**
> **problem** **statement,** **your** **approach,** **paper**
> **structure.**
>
> • **Briefly** **situate** **your** **work** **relative** **to**
> **prior** **approaches** **in** **ASR,** **MT,** **and** **cascaded**
> **ST.** • **Dataset** **statistics,** **audio** **format,**
> **preprocessing** **steps.**
>
> • **Baseline** **and** **improved** **pipeline** **architectures**
> **with** **justifications.** • **Evaluation** **setup,** **metrics,**
> **and** **experimental** **conditions.**
>
> • **Tables** **and** **discussion** **of** **BLEU/chrF++** **scores.**
> • **Qualitative** **analysis** **of** **system** **outputs.**
>
> • **Interpretation** **of** **results,** **limitations,** **and**
> **potential** **improvements.** • **Summary** **of** **contributions**
> **and** **findings.**
>
> • **ACL-style** **bibliography.**

**8.** **Evaluation** **Metrics**

**Required** **Metrics**

> • **Standard** **translation** **quality** **metric.** **Use**
> **SacreBLEU** **for** **reproducibility.**
>
> • **Character-level** **F-score** **metric;** **more** **robust**
> **than** **BLEU** **for** **morphologically** **rich** **languages.**

**Optional** **Metrics**

> • **Neural** **translation** **evaluation** **metric.** **Use**
> **unbabel-comet** **if** **compute** **allows.** • **Word** **Error**
> **Rate** **on** **ASR** **transcriptions** **(if** **you** **have**
> **reference** **transcriptions).**

**Practical** **Diagnostics**

> • Coverage: proportion of input utterances that produce non-empty
> output. • Repetition rate: frequency of degenerate repeated outputs.
>
> • Length ratio: average ratio of hypothesis length to reference
> length.

**9.** **Marking** **Scheme**

The assignment is marked out of 100 and weighted at 50% of the module
total.

||
||
||
||
||
||
||

Deadline: 10 May 2026 \| Page 5

NLP Module — Assignment 2: Irish→English Speech Translation

||
||
||
||
||

**10.** **Distinction-Level** **Expectations**

A distinction (typically 70%+) will typically demonstrate several of the
following:

> • Comparison of more than one ASR front-end (e.g. Whisper-small vs.
> Whisper-medium, or Whisper vs. a Wav2Vec2 Irish model).
>
> • Comparison of more than one MT approach (e.g. NLLB-200 vs. Opus-MT
> or mBART-50). • A well-motivated improvement with clear ablation or
> justification.
>
> • A systematic, categorised error analysis with illustrative examples
> and discussion. • Awareness of the limitations of BLEU/chrF++ in
> low-resource settings.
>
> • A written discussion that situates results within the broader IWSLT
> context. • Polished, publication-ready writing with correctly
> formatted citations.

**11.** **Academic** **Integrity** **and** **AI** **Use**

You are permitted to use AI writing and coding assistants (e.g. ChatGPT,
Claude, Copilot, Gemini). However, the following rules apply:

> • You must disclose any AI tool use in an appendix of your report,
> specifying what was used and how.
>
> • All code and written content must be understood, verified, and
> edited by you. Do not submit unverified AI-generated code.
>
> • All experimental results must be genuinely your own. Do not
> fabricate or adjust numbers.

• The intellectual analysis, interpretation, and critical discussion
must be your own work. Plagiarism detection tools will be applied.
Undisclosed AI use, or submission of work that is substantially
another’s, constitutes academic misconduct and will be dealt with under
university policy.

**12.** **Submission** **Instructions**

Submit all materials as a single ZIP archive via the module submission
portal on Blackboard/Moodle. Name your archive as follows:

> studentID_NLP_Assignment2.zip

The archive should contain:

> • report.pdf — your ACL-format report

Deadline: 10 May 2026 \| Page 6

NLP Module — Assignment 2: Irish→English Speech Translation

> • notebook.ipynb — your Google Colab / Jupyter notebook • README.md —
> brief setup and reproduction instructions
>
> • results/ — directory containing hypothesis files and metric scores

Late submissions will be penalised at 5 marks per day up to a maximum of
5 days, after which a mark of zero will be awarded, in line with
university late work policy. Extensions must be requested via the school
office before the deadline.

> Questions? Post to the module discussion board on Moodle. Please do
> not email for questions that are relevant to all students.

Deadline: 10 May 2026 \| Page 7
