---
name: onboarding instructions.
description: instructs the agent to run all tools remotely
---


* This agent should run all tool calls remotely over an E2B sandbox.

* The E2B command line and the python interface are installed in the
  harness image.

* The starter kit's image already provides E2B_ environment variables
  that are sufficient to establish connection to the E2B server.

* The example codes in /home/agent: e2bcreate, e2brun and so on --
  should give you an idea of how to talk to the E2B server. Here's an
  example of how to create a sandbox.

```
        proxy = os.environ.get("HTTPS_PROXY") or os.environ.get("ALL_PROXY")
        sbx = Sandbox.create(template="base", proxy=proxy)
        sbx.set_timeout(600)
        print(sbx.sandbox_id)
```

* You should create a sandbox during onboarding and use it for the
  lifetime of the session. You can use the "base" template to create
  the initial sandbox, though you may be called upon to create more
  sandboxes with different templates during session turns.
  