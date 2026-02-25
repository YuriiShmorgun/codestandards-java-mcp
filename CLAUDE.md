# Java Code Standards MCP Server

When writing or reviewing any Java code, you **must** fetch and apply rules from the MCP server. Do not rely on general knowledge — always verify against the MCP server first.

## Workflow

**Step 1 — Discover available rules:**
Call `list_categories` and `list_tags` to see all available categories, tags, and rule IDs.
This is always the first step — the rule set grows over time, so never assume what exists.

**Step 2 — Select relevant categories and tags:**
Based on the task, identify which categories and tags apply to the code being written.
Use the names returned in Step 1 — do not guess or hardcode values.

**Step 3 — Fetch rules:**
Call `get_java_rules(categories=[...], tags=[...])` with the selected values.
Call `get_rule_details(rule_ids=[...])` for deeper detail on specific rules.

**Step 4 — Generate and verify:**
Write the code, then check every construct against the fetched rules before returning.
During generation, freely make additional MCP calls at any point if needed — to clarify a rule,
check an edge case, or fetch rules for a construct discovered mid-way.
**Priority is code quality and rule compliance, not minimizing MCP calls.**

## Priority

Rules from the MCP server have **highest priority**. If an MCP rule conflicts with general Java practice — follow the MCP rule.
