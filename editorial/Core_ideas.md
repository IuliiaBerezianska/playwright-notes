# Core Ideas

Це не теми постів.
Це архітектурні ідеї, навколо яких побудований Playwright.

Кожна нова нотатка повинна відповідати на питання:
"Яку головну ідею вона пояснює?"

---

## BrowserContext

**Головна ідея**

BrowserContext — найменша одиниця ізоляції.

Пояснює:
- storageState
- authentication
- context.newPage()
- page.close() vs context.close()
- parallel execution
- multi-user scenarios

---

## Fixtures

**Головна ідея**

Fixtures позбавляють тест відповідальності за керування ресурсами.

Пояснює:
- dependency graph
- setup/teardown
- worker vs test scope
- automatic cleanup
- custom fixtures
- lazy initialization
