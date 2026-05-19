# Skill: /trace

This custom skill tracks and documents the end-to-end execution flow of tool calls within devlens, specifically focusing on `read_file` and `write_file` requests initiated by Claude.

## Purpose
To help developers understand the complete lifecycle of a tool request, ensuring transparency in how the agent interacts with the local file system and how the codebase validates or alters those requests.

## Request/Response Lifecycle Trace

1. **Agent Intent**: Claude determines a file operation is needed and issues a JSON payload containing the tool name (e.g., `read_file`) and arguments (e.g., `path`).
2. **Devlens Interception**: The core agent loop in devlens captures the tool request before execution.
3. **Policy & Permission Check**: Devlens evaluates the request against configuration rules to decide whether to honor, modify, or reject the tool call.
4. **Execution Layer**: If approved, the local file system wrapper executes the native Node.js/Python file system operation.
5. **Result Formatter**: The raw data or error output is structured into a clean string format.
6. **Response Cycle**: The formatted output is packaged and sent back to Claude as tool results, completing the cycle.

## How to Test
Run Claude Code in the repository and invoke the skill:
```bash
/trace read_file
```
