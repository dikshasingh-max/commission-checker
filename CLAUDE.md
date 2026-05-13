# Commission Checker — Claude Instructions

## Daily Briefing: Calendar Blocks

When creating all-day calendar task blocks from daily briefs, always include the following line at the **top of the event description**:

```
⚠️ Set this event to FREE in Google Calendar (Status → Free) so others can still book time.
```

### Why this is needed

The Google Calendar MCP tool (`create_event` / `update_event`) does not expose the `transparency` field, so all-day events are created as **Busy** by default. This blocks colleagues from scheduling over those slots. Until the MCP tool supports transparency, the workaround is:

1. Add the reminder text above to every all-day task block description.
2. After creation, open the event in Google Calendar → Edit → set **Status** to **Free**.

### Template for all-day task blocks

```
summary:     📋 <task title>
allDay:      true
startTime:   <date>T00:00:00Z
endTime:     <next day>T00:00:00Z
description: ⚠️ Set this event to FREE in Google Calendar (Status → Free) so others can still book time.
             ---
             <any additional context>
```
