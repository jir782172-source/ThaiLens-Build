# ThaiLens build source

Experimental Thai-to-Chinese iPhone subtitles. Version 0.9.0 contains recovery for transient network failures and signed configuration updates.

The recovery build passed all 89 XCTest checks, generated 3 iOS subtitle previews, and packaged an unsigned arm64 IPA with its broadcast extension. [Build record](https://github.com/jir782172-source/ThaiLens-Build/actions/runs/45539638589). Actual network switching on the user's iPhone still needs device validation.

Use your own Groq API key on the phone. No API keys, signing certificates, conversation data, audio recordings, or diagnostic logs are included. Diagnostics and signed updates use a separately authorized private repository; its access token is entered on the phone.

The app processes ReplayKit app audio, never the microphone. iOS may restrict capture in calls or protected content. A terminated broadcast must be started manually.

The workflow uses a standard macOS runner, runs regression tests, then packages a single unsigned arm64 IPA including the broadcast extension. Re-sign both targets before installing. Third-party notices are included under Resources/Licenses.
