# בדיקת דיוק ומהימנות — Sigma Knowledge Base כ"Company Brain"

**נבדק:** כל תיקיית `Sigma-Knowledge-Base` (50 מסמכים: md / docx / yaml), התיקייה `.git` וקובץ ה-README הראשי.
**תאריך הבדיקה:** 30.08.2026
**מטרת הבדיקה:** להעריך עד כמה חומרי הידע הקיימים מדויקים, עקביים ואמינים דיים כדי לשמש כמקור אמת יחיד ("company brain") לצוותים שונים בארגון.

---

## תקציר מנהלים

המסקנה המרכזית: **ה-Knowledge Base כרגע הוא לא "company brain" אחד, אלא שני מאגרי ידע נפרדים שלא מדברים זה עם זה**, בתוספת כמה תקלות טכניות קונקרטיות (לא רק "חסר תוכן" אלא שגיאות בפועל בטקסט הקיים) שפוגעות במהימנות שלו.

1. **השכבה הרעיונית/דוקטרינרית** (DOC, OM, PA, PR, RS, KB) — כתובה כולה באנגלית, בסגנון "ניירות עמדה" עשירים. אבל **4 מתוך 5 המסמכים ה"בסיסיים" (Foundational) ריקים למעשה** — כולם רק שלדים עם "Authoring Placeholder". רק PA-001 (ארכיטקטורת הפלטפורמה) כתוב בפועל.
2. **השכבה ההנדסית/עדכנית** (Context-and-Meaning, Geography, Operations-Store, וגם CAT ו-DM) — כתובה בעיקר בעברית, בסגנון PRD/HLD/ADR ממוקד ומחייב (guardrails, Definition of Done, evidence gates). זו ברמת דיוק והבשלה גבוהה בהרבה, אבל **אינה מוזכרת בכלל ב-DOCUMENT_REGISTRY וב-KB-000**, כלומר "מפת השטח" הרשמית של ה-KB לא יודעת שהיא קיימת.
3. יש **שתי תקלות עריכה מוכחות** של כפילות טקסט מלאה (copy-paste) במסמכים "בסיסיים" — לא טעות ניסוח אלא שבירה מבנית בפועל.
4. יש **התנגשות מזהים (ID) ממשית**: לשני מסמכים שונים יש את אותו `id: OM-005` בפרונט-מאטר.
5. **הגלוסר הרשמי (KB-001) לא מכסה כמעט אף מונח מהשימוש בפועל** — כולל מושגי ליבה כמו Evidence Gate, Trust Contract, Capability Mesh, Commander Space/Experience.
6. יש **דריפט שם מוצר לא פתור**: "Commander Space" (בשכבה הישנה) מול "Commander Experience" (בשכבה החדשה) — נראה שזה אותו רכיב, בלי הצהרה מפורשת על שינוי שם.
7. מסמך ה-README הראשי בשורש הריפו (`README.md`) מכיל שתי שורות טקסט בלבד ואינו אומר דבר על מה זה Sigma.

**המשמעות המעשית:** אם צוות חדש ייכנס ל-repo הזה ויתבסס עליו כ"אמת אחת", הוא עלול (א) לפספס לגמרי את כל שכבת ה-Operations-Store / Context & Meaning / Geography כי היא לא מקושרת מהעמוד הראשי, (ב) לקבל תחושה מוטעית שהדוקטרינה, ה-Operating Model והפורטפוליו מוגדרים — כשבפועל הם ריקים, ו-(ג) להיתקל בסתירות שם-מוצר וב-ID שבור בלי שום אזהרה.

---

## מתודולוגיה

נקראו כל 50 הקבצים בתיקיית `Sigma-Knowledge-Base` (כולל שישה קובצי `.docx` שהומרו לטקסט, ושני קובצי `.yaml`), הושוו מול מסמכי הממשל העצמי של ה-KB (`DOCUMENT_REGISTRY.md`, `KB-000`, `KB-001`), ונבדקו: (1) התאמה בין המבנה המוצהר למבנה בפועל, (2) שלמות תוכן מול "Authoring Placeholder"/stub, (3) עקביות מזהים, גרסאות ותאריכים, (4) עקביות מינוח מול הגלוסר, (5) כפילויות/שגיאות טקסט. לא בוצעה הערכה של נכונות עסקית/אסטרטגית של התוכן עצמו (למשל האם "העקרונות האדריכליים" נכונים) — זו שאלת שיפוט מקצועי-ארגוני שחורגת מבדיקת עקביות/דיוק טכני של מסמכים.

---

## ממצא 1 — שני "מוחות" נפרדים שלא מקושרים זה לזה

`DOCUMENT_REGISTRY.md` (גרסה 1.1) ו-`KB-000 – Knowledge Base Guide.md` מגדירים את מבנה ה-KB כ-6 דומיינים בלבד: `DOC, OM, PA, PR, RS` (ועוד `KB` עצמו), עם ARC-001 כ"נקודת כניסה מושגית".

בפועל, בתיקייה קיימים גם: `CAT/`, `DM/`, `Context-and-Meaning/`, `Geography/`, `Operations-Store/` — חמישה תיקיות/דומיינים נוספים, שבהם נמצא חלק ניכר מהתוכן ה"טרי" והמעשי ביותר בכל ה-KB (הכולל תיארוך "August 2026" — מאוחר יותר מתאריך ה-`last_updated: 2026-07-20` שרשום בכל 25 המסמכים בשכבה הישנה).

בדיקה כיוונית של קישורים (grep) הראתה:

- אף אחד מהמסמכים ב-DOC/OM/PA/PR/RS/KB לא מזכיר את Context-and-Meaning, Geography, Operations-Store, Spatial Intelligence, CAT או DM.
- לעומת זאת CAT-001 ו-DM-001 כן מפנים חזרה למסמכי OM/PA/DOC (לדוגמה: `CAT-001` שורה 83–84 מפנה ל-OM-005 ו-PA-009; `DM-001` שורה 74–77 מפנה ל-DOC-001, OM-006, OM-007, OM-008).
- Context-and-Meaning, Geography ו-Operations-Store — שלושת הדומיינים הכי מפורטים וה"מבצעיים" ביותר בכל ה-KB — **לא מפנים בחזרה בכלל** לדוקטרינה/Operating Model/Architecture. אין קישור אחד ל-OM-001, PA-001 וכו'.

**המשמעות:** מי שנכנס דרך `README.md` הראשי או דרך `KB-000`/`DOCUMENT_REGISTRY` בכלל לא ידע שהדומיינים האלה קיימים. מי שנכנס ישירות לתיקיית Operations-Store לא ידע שיש "שכבת דוקטרינה" מעליו. זה לא KB אחד — זו התאחדות פיזית (אותו repo) של שני מאגרים שנכתבו בנפרד.

---

## ממצא 2 — הפניה שבורה: ARC-001 לא קיים

`DOCUMENT_REGISTRY.md` מגדיר את `ARC-001 — Sigma Reference Architecture` כמסמך הבסיסי הראשון ברשימה, כ"נקודת הכניסה המושגית ל-KB" (השורה האחרונה בטבלת ה-Governance), וכפריט הראשון בסדר הקריאה המומלץ ("Reading Order"):

> 1. ARC-001 — Sigma Reference Architecture
> 2. DOC-001 — Sigma Doctrine
> ...

בפועל **אין תיקיית `ARC/` ואין קובץ כזה בשום מקום ב-repo**. משתמש חדש שמנסה לעקוב אחרי סדר הקריאה הרשמי נתקל בקישור שבור כבר בצעד הראשון.

---

## ממצא 3 — 4 מתוך 5 המסמכים ה"בסיסיים" (Foundational) הם קליפה ריקה

טבלת ה-Foundational Architecture ב-`DOCUMENT_REGISTRY.md` מגדירה שישה מסמכי-על: ARC-001 (לא קיים, ראו ממצא 2), DOC-001, OM-001, PA-001, PR-001, RS-001.

בדיקת תוכן בפועל:

| מסמך | סטטוס בפועל | מס' מילים |
|---|---|---|
| DOC-001 Sigma Doctrine | **כל 7 הסעיפים הם "Authoring Placeholder"** — אין משפט תוכן אחד | 655 |
| OM-001 Sigma Operating Model | **כל 10 הסעיפים "Authoring Placeholder"** | 602 |
| PR-001 Sigma Product Portfolio | **כל 7 הסעיפים "Authoring Placeholder"** | 483 |
| RS-001 Sigma Discovery & Research | **כל 8 הסעיפים "Authoring Placeholder"** | 527 |
| PA-001 Sigma Platform Architecture | כתוב במלואו, מפותח לעומק | 5,366 |

כלומר: מתוך ~7,600 המילים הכוללות בשכבת ה"יסודות", **כ-70% (5,366 מילים) מרוכזות במסמך אחד בלבד**, ושאר ארבעת המסמכים — כולל הדוקטרינה שאמורה להיות "המסמך המכונן של Sigma" (כך כתוב במפורש בפתיח של DOC-001) — הם תבנית ריקה. לשם השוואה: מסמכי המשנה (Supporting) תחת OM ו-PA ותחת PR כתובים במלואם ולעיתים באורך ניכר (לדוגמה OM-008 Trust Framework ~30 עמ' תוכן, PR-017 Operational Repositories ~50KB). כלומר **הפירוט קיים — הוא פשוט לא סוכם מעולם חזרה למסמכי-העל**, מה שהופך את "שכבת ה-Executive" ל-*הכי לא אמינה* בכל ה-KB, בדיוק במקום שבו מנהיגות ארגונית וצוותים חדשים היו אמורים להתחיל לקרוא.

בנוסף, שלושה ממסמכי המשנה של PA (PA-007 Context Engine, PA-008 Knowledge Graph, PA-009 Repository Architecture) הם גם הם סטאבים ריקים לגמרי (רק "Populate only from approved existing material"), וכך גם RS-003 Discovery Findings.

---

## ממצא 4 — שתי כפילויות טקסט מלאות (שגיאת copy-paste מוכחת, לא רק "טיוטה")

זו לא בעיית שלמות אלא **תקלת תוכן ממשית** בטקסט שכן קיים:

1. **`PA/PA-001 Sigma Platform Architecture.md`** — כל הפרק "Part II — Sigma Platform Architecture" (מ"The Architectural Perspective" ועד "Transition") **מופיע פעמיים ברצף, מילה במילה** (שורות 333–683 ואז שוב 684–1034, זהות לחלוטין), לפני שהמסמך ממשיך ל-"Part III — Platform Capabilities".
2. **`CAT/CAT-010 — Operations Repository.md`** — פרק "Part IV – Operational Knowledge Lifecycle" (Progressive Knowledge Creation / Continuous Evolution / Historical Continuity / Operational Knowledge Maturity / Living Operational Knowledge) **מופיע פעמיים ברצף, מילה במילה** (שורות 395–507 ואז שוב 508–619). כתוצאה מכך **"Part V" נעלם לגמרי** מהמסמך — המספור קופץ ישר מ-"Part IV" (כפול) ל-"Part VI".

שתי התקלות מצביעות על דפוס עבודה חוזר (העתק-הדבק בזמן איחוד/עריכת מסמכים) שלא עבר QA לפני commit. זה סוג הממצא שהכי מערער אמון: קורא שלא ישים לב יקרא את אותו טקסט פעמיים בלי להבין שמשהו נשמט (Part V ב-CAT-010).

---

## ממצא 5 — התנגשות מזהים (ID collision)

לפי `KB-000`, "Every document must have a unique ID" — זהו כלל ממשל מפורש. בפועל:

- **`OM/OM-006 Trusted Context.md`** — הפרונט-מאטר שלו מכריז `id: OM-005` (במקום OM-006), **בדיוק אותו ID כמו** `OM/OM-005 Operational Assets.md`.

זו שגיאה טכנית קלה לתקן (כנראה נגרמה מהעתקת הפרונט-מאטר של OM-005 כתבנית ל-OM-006 ושכחת עדכון), אבל היא בדיוק סוג הפרט ש"company brain" חייב להיות חסין לו — מערכת אוטומטית או agent שמחפש מסמכים לפי ID עלול להביא את המסמך הלא נכון.

---

## ממצא 6 — הגלוסר הרשמי לא מכסה את השפה בפועל

`KB-001 Sigma Glossary` מוגדר כמקור האמת היחיד לאוצר המילים ("every core concept has a single authoritative definition… documents… should reference these definitions rather than redefine them"), ומכיל 18 מונחים.

בדיקת כיסוי מול מונחי ליבה שבשימוש נרחב בפועל בכל ה-KB:

| מונח | מס' קבצים שמשתמשים בו | מוגדר בגלוסר (KB-001)? |
|---|---|---|
| Operational Signal | 18 | כן (אבל בניסוח שונה מהסכימה בפועל ב-Context-and-Meaning) |
| Commander Space | 14 | **לא** |
| Commander Experience | 12 | **לא** |
| Evidence Gate | 4 | **לא** |
| One Delivery | 5 | **לא** |
| Trust Contract | 2 | **לא** |
| Capability Mesh | 1 | **לא** |

כלומר בפועל, רוב אוצר המילים התפעולי-מוצרי של Sigma (כולל מונחים מרכזיים שיש להם פרק שלם משלהם, כמו One Delivery ו-Trust Contract ב-OM-008/OM-009) פשוט לא קיים במסמך שאמור להיות "השפה המשותפת". זה אומר שהגלוסר לא עודכן מאז שנכתבו רוב מסמכי ה-Domain Papers וה-PRD/HLD המפורטים.

---

## ממצא 7 — דריפט שם מוצר: Commander Space מול Commander Experience

- השכבה הישנה (`PR-014 Commander Space.md`, `PA-010`, `PA-011`, `CAT-001`, `CAT-010`, `DM-001`) — משתמשת עקבית ב-**"Commander Space"** כשם המוצר/הרכיב שאחראי על תמונת מצב וממשק מפקד.
- השכבה החדשה (`Context-and-Meaning`, `Geography`, כל קבצי `Operations-Store`) — משתמשת עקבית ב-**"Commander Experience"** לתיאור אותו תפקיד בדיוק: "בעלים על attention prioritization, presentation, investigation, decision/action" (ר' `01_Context_and_Meaning_PRD.md`, סעיף 4 — טבלת Domain Boundaries).
- בדקנו במפורש: **מסמך PR-014 (המסמך הרשמי של "Commander Space") אף פעם לא מזכיר את המונח "Commander Experience"**, ולהיפך — אף אחד ממסמכי C&M/Geography/Operations-Store לא מזכיר "Commander Space".

אין שום מקום ב-KB שמצהיר "Commander Space שונה שמו ל-Commander Experience" או מסביר שמדובר בשני דברים שונים. צוות שקורא רק את השכבה הישנה או רק את השכבה החדשה לא ידע שיש עוד שם למוצר הזה — סיכון ממשי לבלבול בין-צוותי בדיוק מהסוג שה-KB אמור למנוע.

בנוסף, קיימים בשכבת Operations-Store שלושה מונחים קרובים אך לא מזוהים במפורש כזהים/שונים: **Operations Store** (שכבת המידע), **Operations Management** ("חוויית היצירה והניהול" — מוזכר פעם אחת בלבד, ב-PRD סעיף 1, בלי כל הגדרה נוספת בשום מסמך אחר), ו-**Operations Repository** (`CAT-010`, קונספט ידע/repository). ייתכן ששלושתם נבדלים במכוון, אך "Operations Management" מופיע כמעין ישות רפאים — מוזכר פעם אחת ולא מוגדר איפה.

---

## ממצא 8 — אי-עקביות פורמט ושפה שפוגעת בשימושיות

- **שני קבצים גדולים — `Geography/Spatial-Intelligence.md` (71KB, הקובץ הגדול ביותר בכל ה-KB) ו-`Operations-Store/Operational-Data-Foundation.md` (34KB)** — אינם markdown נקי. הם מכילים תגיות `<span dir="rtl">…</span>` גולמיות המוטבעות בכל שורה (ניכר שהומרו מ-Word/Google Docs בלי ניקוי), וללא כותרות markdown תקניות (`#`) בכלל — כלומר לא ניתן למפות את מבנה המסמך אוטומטית כפי שנעשה לכל שאר הקבצים.
- שאר ה-KB (כולל כל שכבת DOC/OM/PA/PR/RS/KB, ו-CAT/DM) כתוב **כולו באנגלית**. Context-and-Meaning, Geography ו-Operations-Store כתובים **כולם בעברית** (עם מונחים טכניים באנגלית מוטמעים). אין הצהרה במקום כלשהו על מדיניות שפה, מה שמקשה על צוותים בין-לאומיים/גלובליים להשתמש באותו KB.
- שם קובץ עם סיומת כפולה: **`DM/DM-001 Decision Model.md.md`** — שגיאת שמירה טכנית (`.md.md`).
- **כל 25 המסמכים** בשכבה הישנה (DOC/OM/PA/PR/RS/KB) נושאים בדיוק אותו `last_updated: 2026-07-20` — כולל מסמכים "ריקים לגמרי" מול מסמכים "מפותחים לעומק". זה מרמז ששדה התאריך הוא ערך תבנית שהוזן פעם אחת בעת יצירת כל הקבצים ולא עודכן מאז בפועל, ולכן **לא ניתן לסמוך על שדה זה כדי לדעת מה עודכן לאחרונה**.
- קובץ ה-`README.md` הראשי בשורש (לא בתוך Sigma-Knowledge-Base) מכיל אך ורק:
  ```
  # Sigma
  Sigma Initiatives
  ```
  שתי שורות בלבד — אינו מסביר מה זה הפרויקט, איך להתחיל, או מפנה ל-Knowledge Base פנימה.

---

## מה כן עובד טוב

חשוב לאזן את התמונה — לא הכול בעייתי:

- **שכבת ה-Domain Papers של OM** (OM-004 עד OM-009, פרט לבעיית ה-ID) כתובה באיכות גבוהה, עקבית מבחינה מבנית (Executive Summary → Theory → Properties → Design Principles → Governance → Counterarguments → Scenarios → Implications → Key Takeaways בכל מסמך), ובעלת "שרשרת היגיון" ברורה בין המסמכים (Signals → Meaning → Assets → Context → Experience → Trust → Delivery).
- **PA-001** (חוץ מהכפילות) הוא מסמך ארכיטקטורה מפותח ומנומק היטב.
- **Context-and-Meaning, Geography ו-Operations-Store** הם ברמת בשלות **גבוהה משמעותית** מהשכבה הישנה: כוללים PRD + HLD + ADR + Contracts + Schema + Golden E2E + Phase-1 DoD + Guardrails מפורשים ("No arbitrary AI confidence = 83%", "Preserve conflict unless authoritative rule exists" וכו'), תרחישי ייחוס קונקרטיים (RS-01…RS-06), ומטריקות הצלחה מדידות. הניסוח מדויק, בר-ביקורת, ומתאים בדיוק לסטנדרט של "company brain" הנדסי-מוצרי אמיתי. אגב, מסמך ה-PRD של Context & Meaning אף מכריז על עצמו במפורש: *"Status: v0.1 — Company Brain / Handoff"* — כלומר הכותבים כבר חשבו במונחים האלה עבור השכבה הזו.
- הרעיון הארכיטקטוני המרכזי (Signals → Meaning → Trusted Context → Actionable Experience → Trust → Delivery) חוזר בעקביות בשלוש שכבות שונות (Doctrine, Operating Model, Platform Architecture) ללא סתירה מהותית ביניהן — זה כן "single source of truth" תקין ברמת הרעיון עצמו.

---

## המלצות מיידיות (לפי סדר עדיפות)

1. **לאחד רישום**: להוסיף את CAT, DM, Context-and-Meaning, Geography, Operations-Store ל-`DOCUMENT_REGISTRY.md` ול-`KB-000`, ולהוסיף קישורים דו-כיווניים לפחות ברמת "References" בין השכבה הרעיונית לשכבה ההנדסית.
2. **לתקן את שתי הכפילויות** ב-PA-001 וב-CAT-010 (ולבדוק אם תוכן "Part V" ב-CAT-010 קיים במקום אחר וצריך רק לשחזר, או שהוא אבד לגמרי).
3. **לתקן את ה-ID השגוי** ב-OM-006 (מ-`id: OM-005` ל-`id: OM-006`).
4. **להחליט ולתעד רשמית**: Commander Space או Commander Experience — ולעדכן את כל המסמכים הישנים/חדשים בהתאם, כולל הבהרה אם Operations Management הוא ישות נפרדת.
5. **לעדכן את KB-001 Glossary** עם המונחים המרכזיים החסרים (Evidence Gate, Trust Contract, Capability Mesh, Commander Space/Experience, One Delivery ועוד), או לפחות להפנות ממנו לתת-הגלוסרים הפזורים (יש הגדרות "Fact / Signal / Recommendation" מקומיות ב-`05_Context_and_Meaning_Operational_Signal_Schema.md` שלא מקושרות מ-KB-001).
6. **ליצור את ARC-001** (או להסיר את ההפניות אליו מ-DOCUMENT_REGISTRY אם הוחלט לוותר עליו).
7. **לכתוב בפועל את 4 מסמכי-העל** (DOC-001, OM-001, PR-001, RS-001) — התוכן הגולמי כבר קיים בפירוט במסמכי ה-Supporting; זו בעיקר עבודת סינתזה/עריכה ולא מחקר מאפס.
8. **להחליט על מדיניות שפה** אחידה (או לפחות תקציר דו-לשוני לכל מסמך מרכזי), ולנקות את שני הקבצים עם ה-HTML הגולמי.
9. להחליף את שדה ה-`last_updated` הקבוע בתאריך commit אמיתי (יש `.git` בריפו — ניתן להפיק אוטומטית).

---

## מסקנה

התוכן שכן נכתב הוא **ברמה מקצועית גבוהה** — במיוחד שכבת ה-Domain Papers וה-Context-and-Meaning/Geography/Operations-Store. הבעיה היא לא איכות הכתיבה אלא **שלמות, סנכרון וממשל**: כמחצית משכבת ה"יסודות" ריקה, שתי שכבות תוכן לא מקושרות זו לזו, יש שגיאת copy-paste כפולה בפועל, ID כפול, וגלוסר שלא מכסה את השפה שבה שאר המסמכים כתובים.

**לכן: לא מומלץ להציג את ה-KB כרגע כ"company brain" מוגמר וסמכותי לצוותים**, בלי לפחות לתקן את הממצאים הקריטיים (1–5 ברשימת ההמלצות) ולהבהיר לקוראים במפורש שהשכבה הישנה (DOC/OM/PR/RS) היא רעיונית/דראפט ואילו Context-and-Meaning/Geography/Operations-Store היא המפרט המחייב לפיתוח בפועל.
