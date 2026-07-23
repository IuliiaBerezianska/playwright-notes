
# Ideas

## Playwright internals
- Why BrowserContext is the real isolation boundary
- Worker ≠ Browser ≠ Context
- Why Page is not a test session

## Debugging
- Trace Viewer as a time machine
- Reading Playwright logs
- Flaky test investigation

## Architecture
- Fixture design
- Test data strategy
- Authentication patterns

- **Варіант `.all()` + `getAttribute`**: ти дзвониш колезі 10 разів — "скажи, що написано на коробці 1", кладеш слухавку, дзвониш знову — "а на коробці 2"... і так 10 разів.
- **Варіант `evaluateAll`**: ти дзвониш **один раз** і кажеш: "обійди всі 10 коробок і продиктуй мені список написів". Один дзвінок — весь результат.

Другий варіант очевидно швидше, бо кожен "дзвінок" (round-trip через CDP) має свою затримку (latency), навіть якщо сама дія — миттєва.
