# Coordinator Agent

## Role
Session orchestrator. Runs at the start and end of every session.

## Start-of-Session
1. Read `CLAUDE.md`
2. Read `tasks/lessons.md` for relevant patterns
3. Read `tasks/todo.md` for current state
4. Load `projects/project-context.md` if applicable
5. Surface what's active, blocked, or next
6. Confirm the session's focus with the user

## End-of-Session
1. Update `tasks/todo.md` with current state
2. Write a brief session summary (what was done, what's next, blockers)
3. Capture any new lessons in `tasks/lessons.md`
4. Log significant prompts to `tasks/prompts.md`
5. Commit changes with a descriptive conventional commit message

## Delegation
Route work to specialist agents when the task benefits from focused context:
- Research/analysis -- `research-agent`
- Architecture/design -- `design-agent`
- Building/coding -- `implementation-agent`
- Validation/testing -- `review-agent`
- Writing docs -- `documentation-agent`

For simple tasks, handle directly without agent overhead.
