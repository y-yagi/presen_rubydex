---
zoom: 0.85
---

# `rdx`コマンド

* gemには`rdx`コマンドが含まれている

```bash
$ bundle exec rdx help
Usage: rdx <command> [options]

Commands:
  console          Open an interactive session with a populated graph for the current workspace
  dead_code        List dead code candidates in the current workspace
  lint             Run semantic lint rules in the current workspace
  mcp [PATH]       Run the MCP server for AI assistants (workspace defaults to the current dir)
  query <CYPHER>   Run a Cypher query against the workspace graph and print the result.
  skill [ID]       Load a Rubydex skill from the library by id. With no id, list the available skills.
  help             Show this help message
```

* ビルトインのツールはまだ全てexperimentalらしく、変更される可能性があるとのこと
