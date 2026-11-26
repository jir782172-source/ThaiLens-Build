# ThaiLens 0.9.1

Thai-to-Chinese iPhone subtitles with network recovery and automatic translation model fallback.

Uses the user's Groq account: Qwen 3.8 27B is primary; GPT-OSS 120B is the fixed backup on rate limit or model unavailability. Each model honors its own cooldown. If both are limited, the active session waits before trying again. Whisper Large V3 remains the speech recognizer. No provider or key rotation. Use a Free Plan account; the app cannot inspect account billing status and never changes the plan.

HTTP Retry-After and exhausted request/token reset headers are honored. Missing timing metadata uses conservative backoff. Network changes cannot skip quota waits. Capture and existing subtitles remain while waiting; old audio is not buffered for later upload. Recent audio resumes after cooldown. Rate limits cannot be bypassed and uninterrupted availability is not guaranteed.

No API keys, signing certificates, conversation data, recordings, or diagnostic logs are included. Diagnostics and signed configuration remain in the separate private ThaiLens repository. App code updates require installing a newly signed IPA. No microphone capture; iOS can restrict call audio. Real YeeTalk call capture and real-provider translation accuracy require device testing.

Build: unpack the source archive, run scripts/prepare.py, generate with XcodeGen, run XCTest, build arm64 iPhoneOS, then scripts/package_ipa.py. The existing workflow archive filename remains ThaiLens-source-v0.9.zip for compatibility; the enclosed project is version 0.9.1 (10).
