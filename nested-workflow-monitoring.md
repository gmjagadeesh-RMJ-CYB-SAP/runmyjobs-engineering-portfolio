# Following a nested workflow from the monitor

I enhanced an existing RunMyJobs monitor during September to December 2025. Operators needed to keep selected workflows visible, see the most recent execution until a later one replaced it, and investigate the child that mattered inside a larger chain. The lead provided guidance on native navigation, which I incorporated into the enhancement.

## The operator's question

A parent can have several children, and the same child definition can run again under another parent execution. When an operator opens a row, the useful destination is the native Process view for the execution that row represents. The definition name by itself does not identify that execution.

| Review scenario | Expected behaviour |
| --- | --- |
| A selected subchain finishes and no newer execution exists | Keep its latest run visible with its final status. |
| A later execution of the selected workflow appears | Replace the displayed run for that selection. |
| An operator investigates a displayed child | Open the matching native Process view. Filters and exported information support follow-up. |

Testing confirmed that a selected child or subchain could be monitored directly. For a regression check, I would use two parent executions containing the same child definition, then compare the displayed execution reference and the reference opened by navigation.
