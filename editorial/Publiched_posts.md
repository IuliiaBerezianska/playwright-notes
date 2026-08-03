
# Publications

## Playwright Notes #1 — BrowserContext — чому Bob раптом побачив кошик Alice

**Series:** Playwright Notes  
**Number:** #1  
**Status:** Published  
**Platform:** LinkedIn  
**Date published:** 2026-07-XX  

**Topic:**  
BrowserContext / browser state isolation / authentication

**Related guide section:**  
Browser, Context and Page

**Related guide cards:**  
- Q12 — BrowserContext
- Q13 — Page vs BrowserContext

**Links:**  

🔗 LinkedIn post:  https://www.linkedin.com/posts/iulliaberezianska_playwright-notes-1-browsercontext-%D1%87%D0%BE%D0%BC%D1%83-share-7485947854201487361-Q8mh/?utm_source=share&utm_medium=member_desktop&rcm=ACoAAAlY3MUBL06zutAqMAHoQJ-tZ1nQFHQNyZc
-

🔗 Playwright Guide:  
-

**Notes:**  
First publication of the Playwright Notes series.

---

## Playwright Notes #2 — Fixtures — я користувалася ними місяцями, не розуміючи, чому вони працюють

**Series:** Playwright Notes  
**Number:** #2  
**Status:** Published  
**Platform:** LinkedIn  
**Date published:** 2026-07-XX  

**Topic:**  
Fixtures / dependency graph / resource management / setup & teardown

**Core idea:**  
Playwright fixtures remove resource management from the test.  
The test declares what it needs; Playwright builds and cleans up the environment automatically.

**Related guide section:**  
Test Lifecycle: Fixtures and Hooks

**Related guide cards:**  
- Q31 — Fixtures
- Q32 — Test vs Worker Fixtures
- Q33 — Custom Fixtures
- Q34 — Setup and Teardown
- Q35 — Fixture Dependencies

**Links:**  

🔗 LinkedIn post:  https://www.linkedin.com/posts/iulliaberezianska_playwright-notes-2-fixtures-%D1%8F-%D0%BA%D0%BE%D1%80%D0%B8%D1%81%D1%82%D1%83%D0%B2%D0%B0%D0%BB%D0%B0%D1%81%D1%8F-share-7486702417670217730-2xeH/?utm_source=share&utm_medium=member_desktop&rcm=ACoAAAlY3MUBL06zutAqMAHoQJ-tZ1nQFHQNyZc
-

🔗 Playwright Guide:  
https://iuliiaberezianska.github.io/playwright-notes/

**Notes:**  
Explains fixtures through the problem they solve rather than their API. Introduces the architectural idea that tests describe dependencies, while Playwright manages the lifecycle of resources.

## Playwright Notes #3 — Який рядок цього тесту створює Browser?
**Series:** Playwright Notes  
**Number:** #3  
**Status:** Draft  
**Platform:** LinkedIn  
**Date published:** -  
**Topic:**  
Playwright vs Playwright Test packages / Test Runner architecture / fixture dependency graph / worker-scoped Browser
**Core idea:**  
The test never controls Browser creation — it only declares what it needs via fixtures. Playwright Test Runner resolves a dependency graph per test: the worker-scoped Browser is reused, while Context and Page are always created fresh.
**Related guide section:**  
Playwright Basics
**Related guide cards:**  
- Q2 — Playwright vs Playwright Test
**Links:**  
🔗 LinkedIn post:  https://www.linkedin.com/posts/iulliaberezianska_playwright-notes-3-%D0%BF%D0%B8%D1%82%D0%B0%D0%BD%D0%BD%D1%8F-%D1%8F%D0%BA%D0%B5-%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D1%8F%D1%82%D1%8C-share-7487410589795872768-HHtf/?utm_source=share&utm_medium=member_desktop&rcm=ACoAAAlY3MUBL06zutAqMAHoQJ-tZ1nQFHQNyZc
-
🔗 Playwright Guide:  
https://iuliiaberezianska.github.io/playwright-notes/
**Notes:**  
Opens as a mini-interview-style hook ("which line creates Browser? — none"), reveals playwright and @playwright/test as two separate packages/APIs, names test() as a registrar rather than an executor, and lands on an npm-install dependency-tree analogy as the memorable takeaway (replaced an earlier database connection-pool analogy).
---

## Playwright Notes #4 — Що станеться, якщо прибрати async, залишивши await?
**Series:** Playwright Notes  
**Number:** #5  
**Status:** Published  
**Platform:** LinkedIn  
**Date published:** 2026-07-XX  
**Topic:**  
async/await pairing / SyntaxError at parse time / function "slicing" / callback boundary
**Core idea:**  
async and await work only as a pair. async marks a function as "sliceable" — able to pause and resume; await marks where to slice. Removing async while keeping await isn't a runtime bug, it's a SyntaxError caught at parse time, before any code executes.
**Related guide section:**  
JavaScript / TypeScript for Playwright
**Related guide cards:**  
- Q12 — Що таке await насправді і як він "розшифровується" в callback?
**Links:**  
🔗 LinkedIn post:  https://lnkd.in/p/eBVmWG2T
-
🔗 Playwright Guide:  
https://iuliiaberezianska.github.io/playwright-notes/
**Notes:**  
Opens with an honest disclosure that she's not a developer by background — came into automation from manual testing. Hook is a real interview question ("what happens if you remove async but keep await"), reveals the exact SyntaxError message and that it fires at parse time. Reuses the click/waitFor example unwrapped into .then() from the guide to show where the "slice" actually happens. Ends teasing Notes #6 on who returns the callback (event loop).

---

## Playwright Notes #5 — Хто повертає callback на виконання?
**Series:** Playwright Notes  
**Number:** #6  
**Status:** Published  
**Platform:** LinkedIn  
**Date published:** 2026-07-XX  
**Topic:**  
Event loop / V8 vs libuv / call stack / queue
**Core idea:**  
Event loop is not part of V8 — a common misconception. It's implemented in libuv, a separate C library for async I/O, unrelated to JavaScript itself. V8 executes JavaScript, holds the call stack, and processes microtasks; libuv coordinates the event loop and hands control back to V8 when the stack is empty and the queue has a ready callback.
**Related guide section:**  
JavaScript / TypeScript for Playwright
**Related guide cards:**  
- Q13 — Що таке event loop і як він працює з call stack та чергою?
**Links:**  
🔗 LinkedIn post:  
https://lnkd.in/p/erWzMvmh
-
🔗 Playwright Guide:  
https://iuliiaberezianska.github.io/playwright-notes/
**Notes:**  
Continues directly from Notes #5's closing question. Hook is the same "недодевелопер" pattern — assumed answer ("event loop, sure") followed by a deeper question (where does it live) that reveals the V8/libuv misconception. Reuses the click/waitFor example a third time for continuity, walked step by step through call stack / queue / browser. Ends teasing Notes #7 on why there are actually two queues (microtasks vs macrotasks).

---


