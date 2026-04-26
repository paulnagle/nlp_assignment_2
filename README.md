# nlp_assignment_2


 git submodule update --init --recursive


# Whisper translation:
Baseline System: Use Solution 1 (auto-detect) - document this limitation in your report

Improved System: Use Solution 2 (Irish-specific fine-tuned Whisper) - this is a clear improvement and addresses the low-resource challenge

# For improved system - use Irish-specific model
ASR_MODEL_ID = 'jimregan/whisper-small-irish'  # or similar Irish-tuned model

# Search Hugging Face for: "whisper irish" or "whisper ga"
# Examples: 'jimregan/whisper-small-irish', 'ymoslem/whisper-medium-ga2en-v6.3.0-4k-r'

This limitation is actually important for your report - discuss how standard Whisper doesn't support Irish, making this a genuine low-resource challenge requiring fine-tuned models or multilingual approaches.




The <|cy|> token (Welsh) appearing suggests Whisper is misidentifying the language, which is expected since Irish isn't officially supported. This is actually good content for your report - document this as evidence of the low-resource challenge.