# agent.scriptostudio.com

The page that holds a person's API key for Studio's agent, on its own origin.

Apps run in Studio's own page at [scriptostudio.com](https://scriptostudio.com), so they could read anything stored there. Studio loads this page in a frame instead: it can ask the frame for a model's reply, but can't read the key or choose where the key is sent. The key stays in the person's browser, in this origin's storage, and is only ever sent to OpenRouter.

Nothing is written here by hand. Studio's deploy workflow in [scripto-studio](https://github.com/jetpax/scripto-studio) copies the built frame page and the scripts it loads into `app/`, and nothing else. The source is `agent-frame.html` and `libs/agent-frame/frame.js` there.
