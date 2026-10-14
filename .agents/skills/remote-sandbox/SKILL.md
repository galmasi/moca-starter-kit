---
name: remote tool calls
description: instructs the agent to run all tools remotely
---


This agent should run every tool call remotely.

* At the beginning of the session run the following command:

/workspace/e2bcreate

This should return with the ID of a remote sandbox.


* During the session run every tool call as follows:

/workspace/e2brun <sandboxID> <command>

Where sandboxid is from the initial call to e2bcreate.

