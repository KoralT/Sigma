**Spatial Intelligence**

**Product Vision, Strategy & Discovery Framework**

**1. Vision**

**<span dir="rtl">מטרת הדומיין</span>**

<span dir="rtl">לבנות יכולת</span> **Spatial Intelligence <span dir="rtl">ארגונית משותפת</span>**, <span dir="rtl">המאפשרת למוצרים, מערכות ו־</span>Agents <span dir="rtl">להשתמש במידע וביכולות מרחביות בלי שכל</span> Consumer <span dir="rtl">יצטרך</span>:

- <span dir="rtl">לדעת איפה המידע נמצא</span>.

- <span dir="rtl">להכיר את מודל הנתונים של מערכת המקור</span>.

- <span dir="rtl">לבצע אינטגרציה ייעודית לכל</span> Source.

- <span dir="rtl">להבין כיצד המידע מיוצג מרחבית</span>.

- <span dir="rtl">לממש בעצמו יכולות</span> GIS.

- <span dir="rtl">להיות מומחה</span> GIS <span dir="rtl">כדי לשאול שאלה שיש לה ממד מרחבי</span>.

<span dir="rtl">המטרה היא להפוך את המרחב מיכולת שממומשת כיום באופן נקודתי בתוך מערכות שונות ליכולת ארגונית משותפת</span>.

**North Star**

**<span dir="rtl">המשתמש לא צריך לדעת שיש לו שאלת</span> GIS.**

<span dir="rtl">המשתמש פועל מתוך ההקשר המקצועי שלו — שאלה, טקסט, מפה, ישות או</span> Context.

Geography <span dir="rtl">אחראי לאפשר להפוך את הצורך המקצועי לבעיה מרחבית, להשתמש במידע וביכולות המתאימים ולהחזיר</span> **Spatial Evidence** <span dir="rtl">שניתן לצרוך במפה, בטקסט או כמידע מובנה</span>.

**2. The Problem We Are Solving**

<span dir="rtl">כיום מידע בעל משמעות מרחבית ויכולות</span> GIS <span dir="rtl">מפוזרים בין מערכות מקצועיות שונות</span>.

<span dir="rtl">כאשר מוצר או משתמש רוצים לענות על שאלה שיש לה ממד מרחבי, הם נדרשים פעמים רבות</span>:

1.  <span dir="rtl">להבין איזה מידע נדרש</span>.

2.  <span dir="rtl">לדעת באיזו מערכת הוא נמצא</span>.

3.  <span dir="rtl">להתחבר למערכת</span>.

4.  <span dir="rtl">להבין את מודל הנתונים שלה</span>.

5.  <span dir="rtl">להבין את הייצוג המרחבי</span>.

6.  <span dir="rtl">לבצע התאמות ו־</span>Normalization.

7.  <span dir="rtl">ולעיתים לממש בעצמם לוגיקת</span> GIS.

<span dir="rtl">כתוצאה מכך</span>:

- <span dir="rtl">אותו מידע מחובר שוב ושוב על ידי</span> Consumers <span dir="rtl">שונים</span>.

- <span dir="rtl">אותן יכולות</span> GIS <span dir="rtl">ממומשות במספר מוצרים</span>.

- <span dir="rtl">מידע מ־</span>Domains <span dir="rtl">שונים מתקשה "להיפגש</span>".

- <span dir="rtl">שאלות שחוצות מספר מקורות דורשות עבודה ידנית או אינטגרציה ייעודית</span>.

- <span dir="rtl">יכולות מרחביות נשארות תלויות במערכת או באיש</span> GIS <span dir="rtl">שמכיר אותן</span>.

<span dir="rtl">הבעיה שאנחנו רוצים לפתור אינה</span>:

**"<span dir="rtl">אין לנו מאגר גיאוגרפי אחד</span>."**

<span dir="rtl">אלא</span>:

**<span dir="rtl">היכולת להשתמש במידע ובחישוב מרחבי אינה כיום יכולת ארגונית משותפת</span>.**

**3. What Geography Is**

Geography <span dir="rtl">אינו</span>:

- Geography DB.

- <span dir="rtl">אוסף שכבות</span>.

- Central Map Application.

- GIS Chatbot.

- <span dir="rtl">מאגר שאליו חייבים להעתיק את כל המידע</span>.

- <span dir="rtl">תחליף למערכות</span> GIS <span dir="rtl">מקצועיות</span>.

Geography <span dir="rtl">הוא שילוב של שלושה נכסים ארגוניים</span>:

**Spatial Information**

<span dir="rtl">מידע שניתן להשתמש בו בהקשר מרחבי</span>.

**Spatial Capabilities**

<span dir="rtl">פעולות וחישובים מרחביים שניתן לעשות בהם שימוש חוזר</span>.

**Spatial Evidence**

<span dir="rtl">תוצאה מרחבית מובנית, אמינה וניתנת להסבר שניתן להעביר לצרכן</span>.

<span dir="rtl">כלומר</span>:

**SPATIAL INFORMATION**

- 

**SPATIAL CAPABILITIES**

↓

**SPATIAL EVIDENCE**

↓

**CONSUMERS / C&M / AGENTS**

<span dir="rtl">המוצר אינו ה־</span>Database.

**The product is the capability.**

**4. Product Principles**

**4.1 Source Systems remain Source of Truth**

Geography <span dir="rtl">אינו מחליף את המערכות המקצועיות ואינו הופך לבעלים של המידע שלהן</span>.

**4.2 Storage is an implementation decision**

<span dir="rtl">אין דרישה שכל המידע יועתק ל־</span>Geography Store.

<span dir="rtl">בהתאם למקור ולצורך ניתן להשתמש ב־</span>Query, Stream, Replication, Cache, Materialization <span dir="rtl">או</span> Reference.

**4.3 Map is an interface, not the product**

<span dir="rtl">אותו</span> Spatial Evidence <span dir="rtl">צריך להיות ניתן לצריכה על ידי</span>:

- Map.

- API.

- Professional System.

- Context & Meaning.

- Agent.

- Future Consumers.

**4.4 Geography produces Spatial Evidence**

Geography <span dir="rtl">אחראי על העובדה והחישוב המרחבי</span>.

Context & Meaning <span dir="rtl">אחראי על הפרשנות הרחבה</span>:

**"<span dir="rtl">אז מה</span>?"**

**4.5 Derived ≠ Source**

<span dir="rtl">מידע שחושב או נגזר על ידי</span> Geography <span dir="rtl">אינו מוצג כאילו הגיע ישירות ממערכת המקור</span>.

**4.6 Space + Time are shared organizational dimensions**

Domains <span dir="rtl">שאינם מחוברים ישירות יכולים להיפגש דרך</span>:

**<span dir="rtl">איפה</span>?**

**<span dir="rtl">מתי</span>?**

**<span dir="rtl">ומה היחס ביניהם</span>?**

Space <span dir="rtl">ו־</span>Time <span dir="rtl">יכולים לשמש שפה משותפת בין מידע שלא נבנה מלכתחילה כדי לעבוד יחד</span>.

**4.7 Capabilities are driven by questions**

<span dir="rtl">לא נבנה</span> Capability <span dir="rtl">משום שהיא קיימת בעולם ה־</span>GIS.

<span dir="rtl">יכולת נכנסת ל־</span>Roadmap <span dir="rtl">כאשר שאלה מקצועית אמיתית מצדיקה אותה</span>.

**4.8 Use Cases validate capabilities — they do not define the platform**

Use Case <span dir="rtl">הוא הדרך שלנו להוכיח שיש צורך</span>.

<span dir="rtl">הוא אינו בהכרח היחידה שאותה צריך לממש</span>.

**Use Case <span dir="rtl">הוא הסיבה לבנות</span> Capability — <span dir="rtl">אבל הוא לא אמור להיות הצרכן היחיד שלה</span>.**

<span dir="rtl">המטרה היא לזהות מתחת ל־</span>Use Cases <span dir="rtl">את ה־</span>Building Blocks <span dir="rtl">שחוזרים בין שאלות</span>, Consumers <span dir="rtl">ו־</span>Domains.

**4.9 Small composable capabilities over dedicated business logic**

<span dir="rtl">נעדיף יכולות קטנות, ברורות וניתנות להרכבה על פני לוגיקה מרחבית סגורה לכל</span> Use Case.

<span dir="rtl">לדוגמה</span>:

**Discover**

**Resolve**

**Intersect**

**Near**

**Time**

**Compare**

**Aggregate**

<span dir="rtl">השאלה אינה רק</span>:

"<span dir="rtl">האם הצלחנו לממש את ה־</span>Use Case?"

<span dir="rtl">אלא גם</span>:

"<span dir="rtl">איזה</span> Capability <span dir="rtl">בנינו באמצעותו, ובאילו שאלות נוספות ניתן להשתמש בה</span>?"

**4.10 Trust is part of the product**

<span dir="rtl">ככל שרלוונטי</span>, Spatial Evidence <span dir="rtl">צריך לאפשר להבין</span>:

- Source.

- Ownership.

- Time.

- Freshness.

- Precision.

- Confidence.

- Fact Type.

- Derived From.

- Calculation Method.

<span dir="rtl">כל תוצאה צריכה לאפשר לענות</span>:

**<span dir="rtl">על בסיס מה אנחנו טוענים את זה</span>?**

**5. Business Questions Are the Starting Point**

<span dir="rtl">ה־</span>Roadmap <span dir="rtl">של</span> Geography <span dir="rtl">לא יתחיל מרשימת יכולות</span> GIS.

<span dir="rtl">הוא יתחיל משאלות מקצועיות אמיתיות</span>.

<span dir="rtl">לדוגמה מבנית בלבד</span>:

- <span dir="rtl">מה קיים במרחב מסוים</span>?

- <span dir="rtl">מה קרה כאן</span>?

- <span dir="rtl">מה השתנה כאן</span>?

- <span dir="rtl">איזה מידע נמצא קרוב לישות מסוימת</span>?

- <span dir="rtl">איפה מתקיימים מספר תנאים</span>?

- <span dir="rtl">איפה קיימת תופעה בריכוז גבוה</span>?

- <span dir="rtl">איזה</span> Context <span dir="rtl">קיים ביחס למידע חדש</span>?

<span dir="rtl">השאלות המדויקות ייקבעו באמצעות</span> Discovery.

<span dir="rtl">עבור כל שאלה נרצה להבין</span>:

**Business Question**

↓

**Spatial Problem**

↓

**Required Information**

↓

**Reusable Capabilities**

↓

**Spatial Evidence**

**6. From Questions to Reusable Capabilities**

<span dir="rtl">שאלות עסקיות יכולות להיות שונות מאוד זו מזו ברמת הלוגיקה המקצועית, אבל להשתמש באותם</span> Building Blocks <span dir="rtl">מרחביים</span>.

<span dir="rtl">לדוגמה</span>:

| **<span dir="rtl">שאלה עסקית</span>**                    | **Spatial Capabilities <span dir="rtl">אפשריות</span>** |
|----------------------------------------------------------|---------------------------------------------------------|
| <span dir="rtl">מה קרה במרחב של מבצע מתוכנן</span>?      | Context + Discover + Intersect + Time                   |
| <span dir="rtl">איפה יש ריכוז של תופעה מסוימת</span>?    | Discover + Filter + Aggregate                           |
| <span dir="rtl">מה השתנה באזור מסוים</span>?             | Context + Time + Compare                                |
| <span dir="rtl">איזה מידע נמצא קרוב לישות מסוימת</span>? | Resolve + Discover + Near                               |
| <span dir="rtl">טקסט → טיוטת מרשם</span>                 | Extract + Resolve + Generate Geometry + Validate        |

<span dir="rtl">לכן</span>:

**<span dir="rtl">ה־</span>Use Cases <span dir="rtl">אינם ה־</span>Roadmap. <span dir="rtl">הם חומר הגלם שממנו מגלים את ה־</span>Capabilities.**

<span dir="rtl">עבור כל שאלה נבצע</span>:

**Business Question → Spatial Problem → Reusable Capabilities**

<span dir="rtl">ונחפש שלושה דברים</span>.

**<span dir="rtl">חזרתיות</span>**

<span dir="rtl">אילו</span> Capabilities <span dir="rtl">חוזרות במספר שאלות</span>?

Capability <span dir="rtl">שחוזרת שוב ושוב היא</span> Candidate <span dir="rtl">חזק להפוך ליכולת</span> Geography <span dir="rtl">משותפת</span>.

**<span dir="rtl">פערים</span>**

<span dir="rtl">איזו שאלה דורשת</span> Capability <span dir="rtl">שעדיין אינה קיימת או אינה נמצאת בכיוון הנוכחי</span>?

<span dir="rtl">הפערים האלה צריכים להשפיע על ה־</span>Roadmap.

**<span dir="rtl">קומפוזיציה</span>**

<span dir="rtl">האם ניתן לענות על שאלות חדשות באמצעות שילוב של</span> Capabilities <span dir="rtl">שכבר קיימות</span>?

<span dir="rtl">לדוגמה</span>:

**Question**

↓

**Resolve**

↓

**Discover**

↓

**Filter**

↓

**Relate**

↓

**Aggregate**

↓

**Spatial Evidence**

<span dir="rtl">זהו אחד המבחנים המרכזיים לכך שאנחנו בונים</span> Platform <span dir="rtl">ולא אוסף</span> Features.

**7. Product Model**

<span dir="rtl">ברמת המוצר</span>, Geography <span dir="rtl">צריך לאפשר מעבר מ־</span>Context <span dir="rtl">או</span> Question <span dir="rtl">ל־</span>Spatial Evidence.

**QUESTION / CONTEXT**

↓

**SPATIAL INFORMATION**

- 

**SPATIAL CAPABILITIES**

↓

**SPATIAL EVIDENCE**

↓

**CONSUMER / C&M / AGENT**

<span dir="rtl">ה־</span>Spatial Evidence <span dir="rtl">יכול להיות מסוגים שונים</span>:

**Entity Evidence**

<span dir="rtl">ישות נמצאת במקום מסוים</span>.

**Relationship Evidence**

X <span dir="rtl">נמצא בתוך / ליד / חופף ל־</span>Y.

**Measurement Evidence**

<span dir="rtl">מרחק, שטח או מדידה אחרת</span>.

**Change Evidence**

<span dir="rtl">מצב מרחבי השתנה</span>.

**Pattern Evidence**

<span dir="rtl">זוהה</span> Pattern <span dir="rtl">או ריכוז</span>.

**Impact Evidence**

<span dir="rtl">שינוי מרחבי יצר</span> Relationship <span dir="rtl">חדש מול</span> Context <span dir="rtl">אחר</span>.

**Derived Geometry**

Geometry <span dir="rtl">שנוצרה באמצעות חישוב או מתוך</span> Input <span dir="rtl">אחר כגון טקסט</span>.

<span dir="rtl">לא כל הסוגים האלה הם</span> Committed Scope.

<span dir="rtl">הם מייצגים את מרחב המוצר האפשרי</span>.

**8. Product Evolution**

<span dir="rtl">אנחנו מציעים ארבעה שלבים להתפתחות המוצר</span>.

<span dir="rtl">השלבים הם</span> **Product Hypothesis** <span dir="rtl">שייבחן ויעודכן בהתאם ל־</span>Discovery.

**Stage 1 — Foundation**

<span dir="rtl">לאפשר למידע ארגוני להפוך ל־</span>Spatially Usable <span dir="rtl">ולהיצרך דרך</span> Geography.

<span dir="rtl">השאלה</span>:

**<span dir="rtl">האם</span> Consumer <span dir="rtl">יכול להשתמש במידע מרחבי שבבעלות מערכת אחרת בלי לבנות אינטגרציית</span> GIS <span dir="rtl">ייעודית</span>?**

**Stage 2 — Capability Building**

<span dir="rtl">לזהות ולבנות את ה־</span>Capabilities <span dir="rtl">שחוזרות בין השאלות</span>.

<span dir="rtl">לדוגמה</span>:

- Discover.

- Resolve.

- Relate.

- Time.

- Compare.

- Aggregate.

<span dir="rtl">הרשימה אינה</span> Scope <span dir="rtl">סופי</span>.

<span dir="rtl">ה־</span>Discovery <span dir="rtl">יקבע אילו יכולות באמת נדרשות</span>.

**Stage 3 — Composition**

<span dir="rtl">להתחיל לענות על שאלות באמצעות שילוב של</span> Capabilities <span dir="rtl">קיימות</span>.

<span dir="rtl">במקום</span>:

**Question → Dedicated Development**

<span dir="rtl">אנחנו רוצים להגיע ל</span>:

**Question → Existing Capabilities → Composition → Spatial Evidence**

**Stage 4 — Scale**

<span dir="rtl">להרחיב את היכולת ל</span>:

- Sources <span dir="rtl">נוספים</span>.

- Domains <span dir="rtl">נוספים</span>.

- Consumers <span dir="rtl">נוספים</span>.

- <span dir="rtl">סוגי מידע נוספים</span>.

- <span dir="rtl">שאלות נוספות</span>.

<span dir="rtl">מבלי שכל</span> Consumer <span dir="rtl">או שאלה חדשים ידרשו לבנות מחדש את ה־</span>Foundation.

**9. Annual Direction — Current Hypothesis**

<span dir="rtl">החלוקה הבאה היא **כיוון מוצרי ראשוני ולא**</span> **Committed Delivery Plan**.

**Q1 Candidate — Make Spatial**

<span dir="rtl">להוכיח</span> Foundation <span dir="rtl">אמיתי מקצה לקצה</span>:

**Real Source**

↓

**Geography**

↓

**Spatially Usable Information**

↓

**Basic Spatial Question**

↓

**Real Consumer**

**Q2 Hypothesis — Discover & Relate**

<span dir="rtl">להרחיב את היכולת כך שניתן יהיה</span>:

- <span dir="rtl">לגלות מידע ממספר מקורות</span>.

- <span dir="rtl">לענות על "מה נמצא כאן</span>?"

- <span dir="rtl">לחשב</span> Relationships <span dir="rtl">מרחביים בסיסיים</span>.

- <span dir="rtl">לייצר</span> Derived Spatial Evidence.

**Q3 Hypothesis — Change & Impact**

<span dir="rtl">אם ה־</span>Discovery <span dir="rtl">מצדיק זאת</span>:

- <span dir="rtl">להבין מצב מרחבי לאורך זמן</span>.

- <span dir="rtl">לזהות שינוי</span>.

- <span dir="rtl">לחשב מחדש</span> Relationships.

- <span dir="rtl">לזהות</span> Contexts <span dir="rtl">שעבורם נוצר</span> Spatial Impact.

Geography <span dir="rtl">מספק את ה־</span>Evidence.

Context & Meaning <span dir="rtl">אחראי לפרשנות המקצועית</span>.

**Q4 Hypothesis — Analyze & Ask**

<span dir="rtl">אם שאלות המשתמשים מצדיקות זאת</span>:

- <span dir="rtl">להוסיף</span> Analysis Capabilities.

- <span dir="rtl">לתרגם שאלה מקצועית לבעיה מרחבית</span>.

- <span dir="rtl">לבחור</span> Information <span dir="rtl">ו־</span>Capabilities <span dir="rtl">מתאימים</span>.

- <span dir="rtl">להרכיב מספר</span> Capabilities <span dir="rtl">עבור שאלה אחת</span>.

**10. Q1 Candidate Business Slice**

Q1 <span dir="rtl">צריך להוכיח ש־</span>Geography <span dir="rtl">מייצר ערך כיכולת ארגונית משותפת — ולא רק כתשתית</span> GIS.

**<span dir="rtl">הבעיה</span>**

Consumer <span dir="rtl">שרוצה להשתמש במידע מרחבי לא אמור להיות תלוי באופן שבו מערכת המקור מחזיקה ומנגישה אותו</span>.

**<span dir="rtl">השאלה הבסיסית</span>**

**"<span dir="rtl">מה יש במרחב הזה</span>?"**

<span dir="rtl">במונחים עסקיים</span>:

<span dir="rtl">בהינתן</span> Context <span dir="rtl">מרחבי שמעניין אותי, החזר לי את המידע הרלוונטי שנמצא בו</span>.

**Current Vertical Slice Hypothesis**

<span dir="rtl">ה־</span>Consumer:

**Zira / Commander Space**

<span dir="rtl">ה־</span>Context:

<span dir="rtl">מבצע מתוכנן בעל מרשם תכנון מרחבי</span>.

<span dir="rtl">השאלה</span>:

**<span dir="rtl">מה קיים או קרה במרחב שבו מתוכנן המבצע</span>?**

Candidate <span dir="rtl">ראשון לבדיקה</span>:

**<span dir="rtl">האם קיימים אירועים שדווחו במרחב שבו המבצע מתוכנן</span>?**

**Flow**

**Operation**

↓

**Planning Sketch**

↓

**Spatial Context**

↓

**Geography**

- 

**Professional Information Source**

↓

**Spatial Query**

↓

**Spatial Evidence**

↓

**Consumer**

Geography <span dir="rtl">יכול לקבוע עובדה כגון</span>:

**<span dir="rtl">אירוע</span> X <span dir="rtl">נמצא בתוך המרחב של</span> Context Y.**

Geography <span dir="rtl">אינו קובע</span>:

**<span dir="rtl">אירוע</span> X <span dir="rtl">משמעותי למבצע</span> Y.**

<span dir="rtl">המשמעות הרחבה שייכת ל־</span>Context & Meaning <span dir="rtl">או ל־</span>Consumer.

**Q1 Candidate Success**

**<span dir="rtl">בהינתן</span> Context <span dir="rtl">מרחבי אמיתי</span>, Consumer <span dir="rtl">מסוגל לקבל דרך</span> Geography <span dir="rtl">מידע רלוונטי שבבעלות מערכת מקצועית אחרת — ללא אינטגרציה ישירה של ה־</span>Consumer <span dir="rtl">למקור</span>.**

<span dir="rtl">ה־</span>Vertical Slice <span dir="rtl">הזה הוא</span> Hypothesis.

<span dir="rtl">ה־</span>Discovery <span dir="rtl">צריך לאמת אותו או להציע</span> Candidate <span dir="rtl">טוב יותר</span>.

**11. Text → Spatial — Strategic Bet**

<span dir="rtl">במקביל ל־</span>Foundation, <span dir="rtl">נרצה לבחון האם טקסט מקצועי יכול להפוך ל־</span>Spatial Context <span dir="rtl">שניתן להשתמש בו באותו מנגנון</span>.

<span dir="rtl">הכוונה אינה לבנות</span> "AI <span dir="rtl">שמבין כל מסמך</span>".

<span dir="rtl">ה־</span>Hypothesis <span dir="rtl">הוא</span>:

**TEXT**

↓

**SPATIAL ELEMENTS / INTENT**

↓

**RESOLUTION**

↓

**CANDIDATE GEOMETRY**

↓

**HUMAN VALIDATION**

↓

**SPATIAL CONTEXT**

↓

**SAME GEOGRAPHY CAPABILITIES**

<span dir="rtl">אחד ה־</span>Use Cases <span dir="rtl">לבדיקה</span>:

**<span dir="rtl">תיאור/פקודה → טיוטת מרשם תכנון</span>**

<span dir="rtl">ה־</span>Discovery <span dir="rtl">צריך לקבוע</span>:

- <span dir="rtl">האם זה ה־</span>Use Case <span dir="rtl">הנכון</span>.

- <span dir="rtl">איזה</span> Input <span dir="rtl">מתאים</span>.

- <span dir="rtl">איזה</span> Output <span dir="rtl">בעל ערך</span>.

- <span dir="rtl">מה ניתן לבצע אוטומטית</span>.

- <span dir="rtl">איפה נדרש</span> Human Validation.

- <span dir="rtl">מה ייחשב הצלחה</span>.

Text → Spatial <span dir="rtl">הוא</span> POC <span dir="rtl">מקביל ואינו תנאי ל־</span>Q1 Foundation GO.

**12. Product Boundaries**

**Geography**

<span dir="rtl">אחראי על יכולות משותפות כגון</span>:

- Spatial Representation.

- Spatial Discovery.

- Spatial Query.

- Spatial Relationships.

- Spatial Computation.

- Spatial Evidence.

- Trust & Lineage.

<span dir="rtl">יכולות נוספות כגון</span> Change, Impact <span dir="rtl">ו־</span>Analysis <span dir="rtl">ייכנסו בהתאם לצרכים שיאומתו</span>.

**Source Systems**

<span dir="rtl">אחראיות על</span>:

- Source Facts.

- Professional Data.

- Ownership.

- Source Identity.

- Professional Workflows.

**Operations**

<span dir="rtl">אחראי על</span>:

- Operation Identity.

- Operation Core.

- Operational Lifecycle.

- Operational Context.

Geography <span dir="rtl">יכול להשתמש ב־</span>Operation <span dir="rtl">כ־</span>Spatial Context.

<span dir="rtl">הוא אינו מנהל את המבצע</span>.

**Context & Meaning**

<span dir="rtl">אחראי על</span>:

- Relevance.

- Interpretation.

- Meaning.

- "So What?"

- Cross-context reasoning.

**Consumers / Agents**

<span dir="rtl">אחראים בהתאם לתפקידם על</span>:

- Interaction.

- Workflow.

- Presentation.

- Attention.

- Actions.

- Capability orchestration.

Agent <span dir="rtl">אינו</span> Source of Spatial Facts <span dir="rtl">ואינו מחליף את</span> Geography computation.

**13. Out of Scope**

<span dir="rtl">אלא אם</span> Discovery <span dir="rtl">עתידי יצדיק שינוי</span>:

- Geography Store <span dir="rtl">כיעד בפני עצמו</span>.

- <span dir="rtl">העתקת כלל המידע הגיאוגרפי בארגון</span>.

- Central Map Application.

- <span dir="rtl">החלפת מערכות</span> GIS <span dir="rtl">מקצועיות</span>.

- <span dir="rtl">הפיכת</span> Geography <span dir="rtl">ל־</span>SoT <span dir="rtl">של</span> Domains <span dir="rtl">אחרים</span>.

- Mega GIS API.

- Recommendation <span dir="rtl">מקצועי בתוך</span> Geography.

- Derived Evidence <span dir="rtl">ללא</span> Lineage.

- Text → Map <span dir="rtl">מלא כחלק מ־</span>Q1 Foundation.

- <span dir="rtl">בניית</span> GIS Capability <span dir="rtl">ללא שאלה מקצועית</span>.

- Agent <span dir="rtl">שממציא</span> Spatial Logic <span dir="rtl">שאינו</span> Capability <span dir="rtl">מנוהל</span>.

**14. Success Metrics**

<span dir="rtl">לא נמדוד הצלחה בעיקר לפי</span>:

- <span dir="rtl">מספר</span> Sources.

- <span dir="rtl">מספר</span> Layers.

- <span dir="rtl">מספר</span> APIs.

- <span dir="rtl">מספר</span> Maps.

- <span dir="rtl">מספר</span> Algorithms.

<span dir="rtl">המדדים צריכים לשקף האם נבנית יכולת ארגונית משותפת</span>.

**Reuse**

<span dir="rtl">כמה</span> Capabilities <span dir="rtl">משמשות יותר מ־</span>Use Case <span dir="rtl">או</span> Consumer <span dir="rtl">אחד</span>?

**Question Coverage**

<span dir="rtl">אילו שאלות מקצועיות ניתן לענות עליהן שלא ניתן היה לענות עליהן בצורה סבירה קודם</span>?

**Time to Spatial Answer**

<span dir="rtl">כמה עבודה נדרשת מ־</span>Consumer <span dir="rtl">כדי להתחיל לקבל תשובה מרחבית</span>?

**Trust**

<span dir="rtl">האם ניתן להסביר את המקור, הזמן והחישוב שמאחורי</span> Spatial Evidence?

**Composition**

<span dir="rtl">כמה שאלות ניתן לפתור באמצעות שילוב של</span> Capabilities <span dir="rtl">קיימות</span>?

**Marginal Cost of a New Question**

<span dir="rtl">כאשר מגיעה שאלה עסקית חדשה</span>:

**<span dir="rtl">כמה</span> Geography <span dir="rtl">חדש צריך לפתח כדי לענות עליה</span>?**

<span dir="rtl">ככל שהפלטפורמה מתבגרת, העלות המוצרית והטכנולוגית של הוספת שאלה חדשה צריכה לרדת</span>.

<span dir="rtl">זהו מבחן מרכזי לכך שאנחנו בונים</span> Platform.

**15. Discovery Before Commitment**

<span dir="rtl">ה־</span>Vision <span dir="rtl">והכיוון השנתי מגדירים לאן אנחנו חושבים שהמוצר צריך להגיע</span>.

<span dir="rtl">הם אינם מחליפים</span> Discovery.

<span dir="rtl">לפני סגירת ה־</span>Committed Roadmap <span dir="rtl">נדרש</span> Discovery <span dir="rtl">בחמישה תחומים</span>.

**15.1 Business Questions**

<span dir="rtl">לאסוף שאלות אמיתיות מתוך</span> Workflows <span dir="rtl">של משתמשים</span>.

<span dir="rtl">המטרה</span>:

- 10–15 <span dir="rtl">שאלות אמיתיות</span>.

- <span dir="rtl">מתוכן 3–5</span> Anchor Questions.

**15.2 Information & Sources**

<span dir="rtl">עבור כל</span> Anchor Question:

**Question → Information Needed → Source → Owner → Current Consumption → Gap**

<span dir="rtl">לא נתחיל ממיפוי כל המידע הקיים</span>.

<span dir="rtl">נתחיל מהשאלות</span>.

**15.3 Existing GIS Capabilities**

<span dir="rtl">לבדוק מה כבר קיים בארגון</span>.

<span dir="rtl">עבור כל</span> Capability <span dir="rtl">רלוונטית</span>:

**Reuse \| Expose \| Build \| Not Needed**

<span dir="rtl">המטרה היא להימנע מבנייה מחדש של יכולת שכבר קיימת</span>.

**15.4 Question → Capability Decomposition**

<span dir="rtl">עבור כל</span> Anchor Question:

**Business Question**

↓

**Spatial Problem**

↓

**Reusable Capabilities**

↓

**Required Data**

<span dir="rtl">המטרה היא לזהות</span>:

**<span dir="rtl">חזרתיות</span>**

Capabilities <span dir="rtl">שחוזרות בין שאלות</span>.

**<span dir="rtl">פערים</span>**

Capabilities <span dir="rtl">שחסרות</span>.

**<span dir="rtl">קומפוזיציה</span>**

<span dir="rtl">שאלות שניתן לפתור באמצעות שילוב יכולות קיימות</span>.

<span dir="rtl">זהו אחד התוצרים המרכזיים של ה־</span>Discovery.

**15.5 Q1 Vertical Slice Validation**

<span dir="rtl">לאמת או להחליף את ה־</span>Hypothesis <span dir="rtl">הנוכחי</span>:

**Operation Planning Sketch → Spatial Context → Discover information in the same area**

<span dir="rtl">ה־</span>Discovery <span dir="rtl">צריך להחזיר</span>:

**Consumer + Question + Context + Information + Source + Geography Capability + Value**

**15.6 Text → Spatial**

<span dir="rtl">לאסוף דוגמאות אמיתיות שבהן משתמש מתרגם כיום מידע מטקסט למרחב</span>.

<span dir="rtl">לבחור</span> POC <span dir="rtl">ראשון ולהגדיר</span>:

- User / Workflow.

- Input.

- Expected Output.

- Automation.

- Human Validation.

- Success Criteria.

**16. The "Sausage Machine" Test**

<span dir="rtl">אחד הסיכונים המרכזיים הוא לממש כל</span> Use Case <span dir="rtl">כלוגיקה עסקית סגורה</span>:

**Use Case A → Dedicated Logic → Answer A**

**Use Case B → Dedicated Logic → Answer B**

**Use Case C → Dedicated Logic → Answer C**

<span dir="rtl">כך ניתן לייצר ערך בטווח הקצר, אבל כל שאלה חדשה הופכת לפרויקט פיתוח נוסף</span>.

<span dir="rtl">וכאשר סיימנו לממש את רשימת ה־</span>Use Cases — <span dir="rtl">לכאורה סיימנו את</span> Geography.

<span dir="rtl">זו אינה המטרה</span>.

<span dir="rtl">במקום זאת</span>:

**USE CASES**

↓

**DISCOVER COMMON SPATIAL PROBLEMS**

↓

**BUILD REUSABLE CAPABILITIES**

↓

**COMPOSE**

↓

**ANSWER MORE QUESTIONS**

<span dir="rtl">לכן בכל</span> Capability <span dir="rtl">שנרצה להכניס ל־</span>Roadmap <span dir="rtl">נשאל</span>:

1.  <span dir="rtl">איזו שאלה מקצועית מצדיקה אותה</span>?

2.  <span dir="rtl">האם אותה יכולת חוזרת בשאלות נוספות</span>?

3.  <span dir="rtl">האם כבר קיימת יכולת שאפשר להשתמש בה</span>?

4.  <span dir="rtl">האם היא</span> Building Block <span dir="rtl">שנוכל להרכיב בהמשך</span>?

5.  <span dir="rtl">האם הלוגיקה באמת שייכת ל־</span>Geography?

6.  <span dir="rtl">מה יקרה כאשר יגיע</span> Use Case <span dir="rtl">חדש שלא הכרנו</span>?

**<span dir="rtl">אם כל שאלה חדשה דורשת</span> Feature <span dir="rtl">חדש — עדיין לא בנינו</span> Platform.**

**<span dir="rtl">אם שאלה חדשה יכולה להשתמש בעיקר ב־</span>Capabilities <span dir="rtl">שכבר קיימות — אנחנו בכיוון הנכון</span>.**

**17. Discovery Exit Gate**

<span dir="rtl">בסיום ה־</span>Discovery <span dir="rtl">צריך להיות אפשר לענות בבירור על</span>:

**WHO**

<span dir="rtl">מי ה־</span>Consumers <span dir="rtl">הראשונים</span>?

**QUESTIONS**

<span dir="rtl">מהן השאלות המקצועיות שאנחנו רוצים לפתור</span>?

**DATA**

<span dir="rtl">איזה מידע נדרש ואיפה הוא נמצא</span>?

**CAPABILITIES**

<span dir="rtl">מה</span> Geography <span dir="rtl">צריך לדעת לעשות כדי לענות עליהן</span>?

**REUSE**

<span dir="rtl">אילו</span> Capabilities <span dir="rtl">משותפות ליותר מ־</span>Use Case <span dir="rtl">אחד</span>?

**EXISTING**

<span dir="rtl">מה כבר קיים ולא צריך לבנות מחדש</span>?

**Q1**

<span dir="rtl">מהו ה־</span>Vertical Slice <span dir="rtl">הראשון שאנחנו מוכנים להתחייב אליו</span>?

**TEXT → SPATIAL**

<span dir="rtl">מה בדיוק אנחנו רוצים להוכיח</span>?

**ROADMAP**

<span dir="rtl">מה בכיוון השנתי</span>:

**Validated \| Changed \| Removed \| Still Hypothesis**

**PLATFORM TEST**

<span dir="rtl">אם מחר מגיעה שאלה עסקית חדשה — האם אנחנו יכולים להשתמש ב־</span>Capabilities <span dir="rtl">שכבר זיהינו, או שאנחנו צריכים לבנות עוד פתרון ייעודי</span>?

<span dir="rtl">רק לאחר ה־</span>Exit Gate <span dir="rtl">הזה נכון לעבור מ־</span>Product Strategy <span dir="rtl">ל־</span>Committed Scope, Architecture <span dir="rtl">ו־</span>Delivery Planning.

**18. Annual Product Narrative**

<span dir="rtl">אנחנו לא בונים מאגר גיאוגרפי חדש</span>.

<span dir="rtl">אנחנו בונים</span> **Spatial Intelligence Capability <span dir="rtl">ארגונית</span>**.

<span dir="rtl">אנחנו מתחילים משאלות מקצועיות אמיתיות</span>.

<span dir="rtl">באמצעותן אנחנו מגלים אילו</span> Spatial Capabilities <span dir="rtl">צריכות להיות משותפות</span>.

<span dir="rtl">אנחנו מוכיחים אותן באמצעות</span> Use Cases <span dir="rtl">אמיתיים</span>.

<span dir="rtl">לאחר מכן אנחנו מאפשרים להרכיב אותן כדי לענות על יותר שאלות, עבור יותר</span> Domains <span dir="rtl">ויותר</span> Consumers.

<span dir="rtl">היעד אינו</span>:

**GIS for GIS users.**

<span dir="rtl">היעד הוא</span>:

**Spatial Intelligence as an organizational capability.**

<span dir="rtl">וה־</span>North Star <span dir="rtl">נשאר</span>:

**<span dir="rtl">המשתמש לא צריך לדעת שיש לו שאלת</span> GIS.**

<span dir="rtl">האבולוציה שאליה אנחנו מכוונים</span>:

**Questions → Spatial Problems → Capabilities → Composition → Intelligence**

<span dir="rtl">והמבחן שלנו לאורך הדרך</span>:

**<span dir="rtl">ככל שהפלטפורמה מתבגרת, שאלה עסקית חדשה צריכה לדרוש פחות פיתוח</span> Geography <span dir="rtl">ייעודי ויותר שימוש והרכבה של יכולות שכבר קיימות</span>.**

**Geography — Product Discovery**

**<span dir="rtl">מטרת המשימה</span>**

<span dir="rtl">יש לנו כיוון מוצרי ל־</span>Geography <span dir="rtl">ו־</span>Spatial Intelligence, <span dir="rtl">כולל</span> Vision <span dir="rtl">ראשוני</span>, Roadmap <span dir="rtl">שנתי ו־</span>Hypothesis <span dir="rtl">ל־</span>Q1.

<span dir="rtl">לפני שאנחנו סוגרים את ה־</span>Scope <span dir="rtl">ומתחילים לפרק אותו ל־</span>Delivery, <span dir="rtl">המטרה היא לבצע</span> Discovery <span dir="rtl">שיבדוק את ההנחות שלנו ויעזור לנו להבין **מה באמת נכון לבנות כיכולת**</span> **Geography <span dir="rtl">משותפת</span>**.

<span dir="rtl">אנחנו לא מחפשים כרגע</span> Architecture <span dir="rtl">או</span> LLD.

<span dir="rtl">אנחנו רוצים לענות על השאלות</span>:

- <span dir="rtl">אילו שאלות מרחביות אמיתיות קיימות אצל המשתמשים</span>?

- <span dir="rtl">איך פותרים אותן היום</span>?

- <span dir="rtl">איזה מידע נדרש כדי לענות עליהן</span>?

- <span dir="rtl">איפה המידע נמצא ומי הבעלים שלו</span>?

- <span dir="rtl">אילו יכולות</span> GIS <span dir="rtl">כבר קיימות היום</span>?

- <span dir="rtl">אילו יכולות חוזרות בין כמה</span> Use Cases <span dir="rtl">ולכן נכון להפוך אותן ליכולת משותפת</span>?

- <span dir="rtl">מהו ה־</span>Vertical Slice <span dir="rtl">הנכון ל־</span>Q1?

- <span dir="rtl">ומה נכון להוכיח במסגרת</span> Text → Spatial?

<span dir="rtl">ה־</span>Vision <span dir="rtl">וה־</span>Roadmap <span dir="rtl">הקיימים הם **נקודת מוצא לאיתגור ולא תשובה שצריך להצדיק**</span>.

<span dir="rtl">אם ה־</span>Discovery <span dir="rtl">מראה שכיוון מסוים במסמך אינו נכון — המטרה היא להציף את זה</span>.

**1. <span dir="rtl">להבין את השאלות האמיתיות של המשתמשים</span>**

<span dir="rtl">לקיים שיחות עם משתמשים ו־</span>Consumers <span dir="rtl">רלוונטיים ולהביא שאלות אמיתיות מתוך העבודה שלהם</span>.

<span dir="rtl">אנחנו לא מחפשים בקשות כמו</span>:

"<span dir="rtl">אני רוצה</span> Heatmap."

"<span dir="rtl">אני צריך שכבה</span>."

"<span dir="rtl">צריך</span> Routing."

<span dir="rtl">אלא את השאלה שהמשתמש מנסה לענות עליה</span>.

<span dir="rtl">לדוגמה</span>:

- <span dir="rtl">מה אני צריך לדעת על המרחב שאני מסתכל עליו</span>?

- <span dir="rtl">מה קרה במרחב מסוים</span>?

- <span dir="rtl">מה השתנה מאז הפעם הקודמת</span>?

- <span dir="rtl">איזה מידע נמצא בתוך אזור מסוים</span>?

- <span dir="rtl">אילו דברים נמצאים קרוב לישות מסוימת</span>?

- <span dir="rtl">איפה מתקיימים כמה תנאים יחד</span>?

<span dir="rtl">אלו דוגמאות למבנה של שאלה בלבד — השאלות שנכניס ל־</span>Discovery <span dir="rtl">צריכות להגיע מהמשתמשים עצמם</span>.

**<span dir="rtl">בכל שיחה צריך להבין</span>**

- <span dir="rtl">מה השאלה שהמשתמש מנסה לענות עליה</span>?

- <span dir="rtl">באיזה</span> Workflow <span dir="rtl">היא עולה</span>?

- <span dir="rtl">כמה פעמים היא עולה</span>?

- <span dir="rtl">איך הוא עונה עליה היום</span>?

- <span dir="rtl">באילו מערכות הוא משתמש</span>?

- <span dir="rtl">האם הוא עובר בין כמה מערכות</span>?

- <span dir="rtl">האם הוא מחבר מידע ידנית</span>?

- <span dir="rtl">האם הוא נעזר באיש</span> GIS?

- <span dir="rtl">כמה זמן / עבודה זה דורש</span>?

- <span dir="rtl">מה הוא לא מצליח לעשות היום</span>?

- <span dir="rtl">ומה הוא עושה אחרי שהוא מקבל את התשובה</span>?

<span dir="rtl">חשוב להביא דוגמאות אמיתיות ולא להסתפק בתיאור כללי של הצורך</span>.

**<span dir="rtl">תוצר</span>**

<span dir="rtl">רשימה של כ־10–15 שאלות עסקיות אמיתיות</span>.

<span dir="rtl">מתוכן — המלצה על</span> **3–5 Anchor Questions** <span dir="rtl">שלדעתך</span> Geography <span dir="rtl">צריך להתמקד בהן</span>.

**2. <span dir="rtl">להבין איזה מידע נדרש</span>**

<span dir="rtl">אחרי שיש לנו שאלות אמיתיות, לוקחים כל אחת מהשאלות המרכזיות ועובדים אחורה</span>.

<span dir="rtl">לא מתחילים ממיפוי של כל שכבות ומאגרי המידע בארגון</span>.

<span dir="rtl">מתחילים מהשאלה</span>.

**<span dir="rtl">לכל שאלה לבדוק</span>**

- <span dir="rtl">איזה מידע נדרש כדי לענות עליה</span>?

- <span dir="rtl">באיזו מערכת הוא נמצא</span>?

- <span dir="rtl">מי הבעלים שלו</span>?

- <span dir="rtl">מהו ה־</span>Source of Truth?

- <span dir="rtl">האם המידע כבר כולל</span> Geometry?

- <span dir="rtl">אם לא — האם ניתן לקשור אותו למרחב</span>?

- <span dir="rtl">האם יש לו משמעות של זמן</span>?

- <span dir="rtl">באיזו תדירות הוא משתנה</span>?

- <span dir="rtl">כמה</span> Fresh <span dir="rtl">הוא צריך להיות עבור השאלה</span>?

- <span dir="rtl">איך צורכים אותו היום</span>?

- <span dir="rtl">האם קיימים כבר</span> Consumers <span dir="rtl">אחרים שהתחברו אליו</span>?

- <span dir="rtl">האם קיימים כמה ייצוגים שונים של אותו מידע</span>?

**<span dir="rtl">תוצר</span>**

<span dir="rtl">עבור השאלות המרכזיות</span>:

**Question → Information Needed → Source → Owner → Current Consumption → Gap**

<span dir="rtl">המטרה היא לדעת איזה מידע באמת נדרש כדי לפתור בעיות משתמש — ולא לבנות רשימת</span> Sources <span dir="rtl">שאנחנו רוצים לחבר כי הם קיימים</span>.

**3. <span dir="rtl">להבין מה כבר קיים היום</span>**

<span dir="rtl">לפני שאנחנו מחליטים לבנות יכולת</span> Geography <span dir="rtl">חדשה, צריך להבין מה כבר קיים היום בארגון</span>.

<span dir="rtl">לעבור על מערכות, תשתיות ויכולות קיימות ולבדוק למשל</span>:

- <span dir="rtl">חיפוש לפי אזור</span>.

- <span dir="rtl">זיהוי מה נמצא בתוך שטח</span>.

- <span dir="rtl">חפיפות</span>.

- <span dir="rtl">קרבה ומרחק</span>.

- Aggregation.

- Heatmaps.

- Routing / Reachability.

- Terrain / Visibility.

- <span dir="rtl">השוואת מצב לאורך זמן</span>.

- <span dir="rtl">חיפוש מקום או ישות מטקסט</span>.

- <span dir="rtl">יצירת</span> Geometry.

- <span dir="rtl">עבודה עם</span> Raster / Coverage, <span dir="rtl">אם רלוונטי לשאלות שמצאנו</span>.

<span dir="rtl">זו אינה משימת</span> Architecture.

<span dir="rtl">המטרה היא להבין</span>:

- <span dir="rtl">האם היכולת קיימת</span>?

- <span dir="rtl">איפה</span>?

- <span dir="rtl">מי משתמש בה</span>?

- <span dir="rtl">האם היא ממומשת בצורה נקודתית בתוך מוצר</span>?

- <span dir="rtl">האם קיימת תשתית משותפת שכבר נותנת אותה</span>?

- <span dir="rtl">האם ניתן לעשות בה</span> Reuse?

- <span dir="rtl">האם כמה מוצרים בנו את אותה יכולת בנפרד</span>?

**<span dir="rtl">תוצר</span>**

<span dir="rtl">עבור היכולות שמצאנו</span>:

**<span dir="rtl">קיים ואפשר להשתמש \| קיים אבל צריך להנגיש \| חסר \| לא ברור שיש בו צורך</span>**

**4. <span dir="rtl">לפרק את השאלות ל־</span>Reusable Capabilities**

<span dir="rtl">זהו אחד התוצרים החשובים ביותר של ה־</span>Discovery.

<span dir="rtl">השאלות העסקיות שאנחנו מקבלים יכולות להיות שונות מאוד זו מזו</span>.

<span dir="rtl">לדוגמה</span>:

| **<span dir="rtl">שאלה עסקית</span>**                    | **<span dir="rtl">מה</span> Geography <span dir="rtl">צריך לדעת לעשות</span>** |
|----------------------------------------------------------|--------------------------------------------------------------------------------|
| <span dir="rtl">מה קרה במרחב של מבצע מתוכנן</span>?      | Context + Discover + Intersect + Time                                          |
| <span dir="rtl">איפה יש ריכוז של תופעה מסוימת</span>?    | Discover + Filter + Aggregate                                                  |
| <span dir="rtl">מה השתנה באזור מסוים</span>?             | Context + Time + Compare                                                       |
| <span dir="rtl">איזה מידע נמצא קרוב לישות מסוימת</span>? | Resolve + Discover + Near                                                      |
| <span dir="rtl">טקסט → טיוטת מרשם</span>                 | Extract + Resolve + Generate Geometry + Validate                               |

<span dir="rtl">השאלות עצמן אינן ה־</span>Roadmap.

**<span dir="rtl">ה־</span>Use Cases <span dir="rtl">הם חומר הגלם שממנו אנחנו מגלים את ה־</span>Capabilities <span dir="rtl">ש־</span>Geography <span dir="rtl">צריך לספק</span>.**

<span dir="rtl">לכן עבור כל שאלה עסקית שנבחרה צריך לבצע</span>:

**Business Question → Spatial Problem → Reusable Capabilities**

**<span dir="rtl">לדוגמה</span>**

<span dir="rtl">שאלה עסקית</span>:

**"<span dir="rtl">מה קרה במרחב של מבצע מתוכנן</span>?"**

<span dir="rtl">לא בהכרח הופכת ל־</span>Feature <span dir="rtl">בשם</span>:

Events in Planned Operation.

<span dir="rtl">במקום זאת צריך להבין אילו</span> Building Blocks <span dir="rtl">נדרשים כדי לענות עליה</span>:

**Operation Context**

- 

**Time**

- 

**Discover**

- 

**Intersect**

↓

**Spatial Evidence**

<span dir="rtl">אותם</span> Building Blocks <span dir="rtl">יכולים בהמשך לענות גם על שאלות אחרות</span>.

**5. <span dir="rtl">לחפש חזרתיות, פערים וקומפוזיציה</span>**

<span dir="rtl">לאחר פירוק השאלות, צריך להסתכל על כולן יחד</span>.

<span dir="rtl">אנחנו מחפשים שלושה דברים</span>.

**5.1 <span dir="rtl">חזרתיות</span>**

<span dir="rtl">אילו</span> Capabilities <span dir="rtl">חוזרות במספר שאלות</span>?

<span dir="rtl">לדוגמה, אם</span>:

**Discover**

**Intersect**

**Time**

**Resolve**

<span dir="rtl">מופיעות שוב ושוב בשאלות שונות — כנראה שמדובר ביכולות</span> Core <span dir="rtl">שכדאי לבנות פעם אחת בצורה משותפת</span>.

<span dir="rtl">ככל ש־</span>Capability <span dir="rtl">משרתת יותר משאלה אחת, יש הצדקה חזקה יותר להפוך אותה ליכולת של</span> Geography.

**5.2 <span dir="rtl">פערים</span>**

<span dir="rtl">איזו שאלה דורשת</span> Capability <span dir="rtl">שלא נמצאת היום בכיוון שלנו</span>?

<span dir="rtl">לדוגמה, יכול להיות שה־</span>Discovery <span dir="rtl">יראה שיכולת מסוימת שחשבנו שתהיה חשובה בכלל אינה נדרשת, ומנגד</span> Capability <span dir="rtl">שלא נמצאת ב־</span>Roadmap <span dir="rtl">חוזרת שוב ושוב אצל משתמשים</span>.

<span dir="rtl">במקרה כזה — ה־</span>Roadmap <span dir="rtl">צריך להשתנות</span>.

**5.3 <span dir="rtl">קומפוזיציה</span>**

<span dir="rtl">צריך לבדוק האם שאלות מתקדמות יותר יכולות להיפתר באמצעות שילוב של</span> Capabilities <span dir="rtl">שכבר זיהינו</span>.

<span dir="rtl">לדוגמה</span>:

**Question**

↓

**Resolve**

↓

**Discover**

↓

**Filter**

↓

**Relate**

↓

**Aggregate**

↓

**Spatial Evidence**

<span dir="rtl">המטרה היא לא שכל שאלה חדשה תדרוש לוגיקה חדשה</span>.

<span dir="rtl">המטרה היא שככל שהמוצר מתבגר, יותר שאלות יוכלו להיפתר באמצעות **הרכבה של יכולות קיימות**</span>.

**6. <span dir="rtl">לאמת את ה־</span>Vertical Slice <span dir="rtl">של</span> Q1**

<span dir="rtl">כרגע קיים</span> Hypothesis <span dir="rtl">ראשון ל־</span>Q1:

<span dir="rtl">למבצע מתוכנן קיים מרשם תכנון מרחבי</span>.

Geography <span dir="rtl">משתמש במרשם כ־</span>Spatial Context <span dir="rtl">ומאפשר לזהות מידע ממערכת מקצועית אחרת שנמצא באותו מרחב</span>.

<span dir="rtl">אחת הדוגמאות</span>:

**<span dir="rtl">האם אירוע התרחש במרחב שבו קיים מבצע מתוכנן</span>?**

<span dir="rtl">ה־</span>Hypothesis <span dir="rtl">הזה צריך לעבור</span> Validation <span dir="rtl">מול משתמשים ולא להפוך אוטומטית ל־</span>Scope.

**<span dir="rtl">צריך לבדוק</span>**

- <span dir="rtl">האם זו באמת שאלה שהמשתמשים שואלים</span>?

- <span dir="rtl">מי שואל אותה</span>?

- <span dir="rtl">מתי</span>?

- <span dir="rtl">איך עונים עליה היום</span>?

- <span dir="rtl">האם מרשם התכנון הוא</span> Context <span dir="rtl">נכון להתחיל ממנו</span>?

- <span dir="rtl">האם הוא קיים בזמן שבו נדרש המידע</span>?

- <span dir="rtl">איזה מידע המשתמש באמת רוצה לראות ביחס אליו</span>?

- <span dir="rtl">האם</span> Events <span dir="rtl">הם ה־</span>Information <span dir="rtl">הנכון ל־</span>Slice <span dir="rtl">הראשון</span>?

- <span dir="rtl">האם קיים</span> Candidate <span dir="rtl">פשוט יותר או בעל ערך גבוה יותר</span>?

- <span dir="rtl">מה המשתמש עושה עם התוצאה</span>?

- <span dir="rtl">מה</span> Geography <span dir="rtl">מאפשר כאן שלא היה אפשר לעשות בצורה סבירה קודם</span>?

**<span dir="rtl">תוצר</span>**

<span dir="rtl">המלצה על</span> Vertical Slice <span dir="rtl">אחד ל־</span>Q1:

**Consumer → Business Question → Context → Information → Source → Geography Capability → Value**

<span dir="rtl">אם ה־</span>Use Case <span dir="rtl">הנוכחי אינו הטוב ביותר — להביא חלופה</span>.

**7. Text → Spatial Discovery**

Text → Spatial <span dir="rtl">הוא</span> Bet <span dir="rtl">שאנחנו רוצים לבדוק במקביל</span>.

<span dir="rtl">המטרה אינה לבדוק</span>:

"<span dir="rtl">האם</span> AI <span dir="rtl">יודע לייצר</span> Polygon?"

<span dir="rtl">אלא להבין</span>:

**<span dir="rtl">באילו</span> Workflows <span dir="rtl">אמיתיים קיים היום מידע מרחבי בתוך טקסט שהמשתמש צריך לתרגם ידנית למפה</span>?**

**<span dir="rtl">צריך לאסוף דוגמאות אמיתיות ולבדוק</span>**

- <span dir="rtl">מה המשתמש קורא</span>?

- <span dir="rtl">מה מתוך הטקסט הוא צריך להבין מרחבית</span>?

- <span dir="rtl">מה הוא מסמן או מצייר היום</span>?

- <span dir="rtl">מה ניתן להבין בצורה חד־משמעית</span>?

- <span dir="rtl">איפה קיימת עמימות</span>?

- <span dir="rtl">מה דורש ידע מקצועי</span>?

- <span dir="rtl">מה ניתן להציע כטיוטה</span>?

- <span dir="rtl">מה חייב לעבור תיקוף משתמש</span>?

- <span dir="rtl">האם התוצאה נכנסת לאחר מכן לאותן</span> Capabilities <span dir="rtl">של</span> Geography?

<span dir="rtl">אחד ה־</span>Use Cases <span dir="rtl">שצריך לבדוק הוא</span>:

**<span dir="rtl">תיאור/פקודה → טיוטת מרשם תכנון</span>**

<span dir="rtl">אבל אין להניח מראש שזה בהכרח ה־</span>Use Case <span dir="rtl">הראשון</span>.

**<span dir="rtl">תוצר</span>**

<span dir="rtl">המלצה ל־</span>Text → Spatial POC <span dir="rtl">ראשון</span>:

- User / Workflow.

- Input.

- Expected Output.

- <span dir="rtl">מה המערכת צריכה לדעת לעשות</span>.

- <span dir="rtl">מה נשאר באחריות המשתמש</span>.

- <span dir="rtl">מה ייחשב הצלחה</span>.

- <span dir="rtl">איך התוצר מתחבר ל־</span>Geography Core <span dir="rtl">ולא נשאר</span> Demo <span dir="rtl">נפרד</span>.

**8. <span dir="rtl">לאתגר את ה־</span>Roadmap <span dir="rtl">השנתי</span>**

<span dir="rtl">ה־</span>Roadmap <span dir="rtl">הקיים מציע כרגע אבולוציה</span>:

**Q1 — Make Spatial**

↓

**Q2 — Discover & Relate**

↓

**Q3 — Change & Impact**

↓

**Q4 — Analyze & Ask**

<span dir="rtl">ה־</span>Discovery <span dir="rtl">לא נועד להוכיח שהחלוקה הזו נכונה</span>.

<span dir="rtl">צריך להשתמש במה שנלמד כדי לאתגר אותה</span>.

<span dir="rtl">לבדוק</span>:

- <span dir="rtl">האם</span> Q1 <span dir="rtl">באמת צריך להתחיל ב־</span>Make Spatial?

- <span dir="rtl">האם</span> Discover <span dir="rtl">ו־</span>Relate <span dir="rtl">הם היכולות הבאות בעלות הערך הגבוה ביותר</span>?

- <span dir="rtl">האם</span> Change & Impact <span dir="rtl">הוא צורך מספיק משמעותי כדי להצדיק שלב בפני עצמו</span>?

- <span dir="rtl">האם קיימות שאלות שמביאות אותנו ל־</span>Analysis <span dir="rtl">מוקדם יותר</span>?

- <span dir="rtl">האם</span> Capabilities <span dir="rtl">מסוימות שתכננו ל־</span>Q4 <span dir="rtl">למעשה נדרשות כבר קודם</span>?

- <span dir="rtl">האם משהו שנמצא היום ב־</span>Roadmap <span dir="rtl">כלל אינו נדרש</span>?

- <span dir="rtl">האם נכון לבנות</span> Capability <span dir="rtl">בעצמנו או להשתמש ביכולת קיימת</span>?

**<span dir="rtl">תוצר</span>**

<span dir="rtl">המלצה על</span> Roadmap <span dir="rtl">מעודכן</span>:

**Validated / Changed / Removed / Still Hypothesis**

<span dir="rtl">אין חובה לשמור על המבנה הרבעוני הנוכחי אם ה־</span>Evidence <span dir="rtl">מצביע על כיוון אחר</span>.

**9. <span dir="rtl">הסיכון שאנחנו רוצים להימנע ממנו — "מכונת נקניקיות</span>"**

<span dir="rtl">אחד הסיכונים המרכזיים הוא לקבל מספר</span> Use Cases <span dir="rtl">עסקיים מוגדרים היטב ולממש כל אחד מהם כפתרון סגור</span>.

<span dir="rtl">כלומר</span>:

**Use Case A → <span dir="rtl">לוגיקה ייעודית → תשובה</span> A**

**Use Case B → <span dir="rtl">לוגיקה ייעודית → תשובה</span> B**

**Use Case C → <span dir="rtl">לוגיקה ייעודית → תשובה</span> C**

<span dir="rtl">זה יכול לתת ערך בטווח הקצר, אבל אז כל</span> Use Case <span dir="rtl">חדש הופך לפרויקט פיתוח נוסף</span>.

<span dir="rtl">וכאשר סיימנו לממש את רשימת ה־</span>Use Cases — <span dir="rtl">לכאורה "סיימנו את</span> Geography".

<span dir="rtl">זו אינה המטרה</span>.

<span dir="rtl">אנחנו רוצים להשתמש ב־</span>Use Cases <span dir="rtl">כדי לגלות ולבנות **יכולות מרחביות משותפות**</span>.

<span dir="rtl">לכן</span>:

**Use Case <span dir="rtl">הוא הסיבה לבנות</span> Capability — <span dir="rtl">אבל הוא לא אמור להיות הצרכן היחיד שלה</span>.**

<span dir="rtl">לדוגמה</span>:

<span dir="rtl">במקום לבנות</span>:

**"<span dir="rtl">הצג אירועים במרחב של מבצע</span>"**

<span dir="rtl">כיכולת ייעודית אחת</span>,

<span dir="rtl">נרצה לזהות מתחתיה</span>:

**Context + Discover + Intersect + Time**

<span dir="rtl">ואז לבדוק אילו שאלות נוספות יכולות להשתמש באותם</span> Building Blocks.

**10. <span dir="rtl">איך אנחנו מצפים שהמוצר יתפתח</span>**

**<span dir="rtl">שלב 1</span> — Foundation**

<span dir="rtl">לדעת להכניס ולצרוך מידע מרחבי בצורה משותפת</span>.

**<span dir="rtl">שלב 2</span> — Capability Building**

<span dir="rtl">לבנות את היכולות שחוזרות בין השאלות, לדוגמה</span>:

**Discover**

**Resolve**

**Relate**

**Time**

**Compare**

**Aggregate**

<span dir="rtl">לא מדובר כרגע ברשימת</span> Scope <span dir="rtl">סופית — ה־</span>Discovery <span dir="rtl">צריך לקבוע מה באמת נדרש</span>.

**<span dir="rtl">שלב 3</span> — Composition**

<span dir="rtl">להתחיל לענות על שאלות חדשות באמצעות שילוב של</span> Capabilities <span dir="rtl">קיימות</span>.

<span dir="rtl">במקום</span>:

**Question → New Development**

<span dir="rtl">אנחנו רוצים להגיע ל</span>:

**Question → Existing Capabilities → Composition → Spatial Evidence**

**<span dir="rtl">שלב 4</span> — Scale**

<span dir="rtl">להרחיב</span>:

- Sources.

- Domains.

- Consumers.

- <span dir="rtl">סוגי מידע</span>.

- <span dir="rtl">שאלות</span>.

- Capabilities <span dir="rtl">חדשות כאשר יש הצדקה</span>.

<span dir="rtl">מבלי שכל</span> Consumer <span dir="rtl">או שאלה חדשים ידרשו לבנות מחדש את ה־</span>Foundation.

**11. <span dir="rtl">איך נראית הצלחה</span>**

<span dir="rtl">הצלחה אינה מצב שבו לצוות</span> Geography <span dir="rtl">יש אינסוף</span> Features <span dir="rtl">לפתח</span>.

<span dir="rtl">להפך</span>.

<span dir="rtl">ככל שהיכולת הארגונית מתבגרת, אנחנו מצפים שיותר שאלות יוכלו להיפתר באמצעות מה שכבר בנינו</span>.

**<span dir="rtl">שאלה עסקית חדשה צריכה לדרוש פחות ופחות פיתוח</span> Geography <span dir="rtl">ייעודי, ויותר שימוש והרכבה של</span> Capabilities <span dir="rtl">קיימות</span>.**

<span dir="rtl">זה אחד הסימנים המרכזיים לכך שבנינו</span> Platform <span dir="rtl">ולא אוסף פתרונות נקודתיים</span>.

<span dir="rtl">העבודה של</span> Geography <span dir="rtl">לא "נגמרת" כאשר ה־</span>Use Cases <span dir="rtl">הראשונים מומשו</span>.

<span dir="rtl">היא משתנה</span>:

<span dir="rtl">מ־</span>

**<span dir="rtl">בניית פתרון לכל</span> Use Case**

<span dir="rtl">ל־</span>

**<span dir="rtl">בניית והרחבת</span> Spatial Capabilities <span dir="rtl">משותפות</span>**

<span dir="rtl">ובהמשך ל־</span>

**<span dir="rtl">פתיחת היכולות לעוד מידע</span>, Domains <span dir="rtl">ו־</span>Consumers, <span dir="rtl">שיפור</span> Trust, Scale <span dir="rtl">ויכולת להרכיב תשובות חדשות</span>.**

**12. <span dir="rtl">תוצר סופי של ה־</span>Discovery**

<span dir="rtl">לא נדרש מסמך מחקר ארוך</span>.

<span dir="rtl">נדרש</span> Product Decision Pack <span dir="rtl">שמאפשר לקבל החלטות</span>.

**1. Business Questions**

10–15 <span dir="rtl">שאלות אמיתיות שנאספו, ומתוכן 3–5</span> Anchor Questions.

**2. Question Decomposition**

<span dir="rtl">לכל</span> Anchor Question:

**Business Question → Spatial Problem → Required Capabilities → Required Data**

**3. Information & Sources**

<span dir="rtl">איזה מידע נדרש, איפה הוא נמצא, מי הבעלים ואיך הוא נצרך היום</span>.

**4. Existing Capability Map**

**Reuse \| Expose \| Build \| Not Needed**

**5. Reusable Capability Map**

<span dir="rtl">אילו</span> Capabilities <span dir="rtl">חוזרות בין השאלות ומה נראה כ־</span>Core <span dir="rtl">של</span> Geography.

**6. Q1 Recommendation**

Vertical Slice <span dir="rtl">אחד שאנחנו ממליצים להתחייב אליו ולמה</span>.

**7. Text → Spatial Recommendation**

Use Case <span dir="rtl">ראשון</span> + Scope + Success Criteria.

**8. Roadmap Challenge**

<span dir="rtl">מה במסמך הקיים</span>:

**Validated \| Changed \| Removed \| Still Hypothesis**

**13. <span dir="rtl">שאלות שאני מצפה שמנהל המוצר יאתגר</span>**

<span dir="rtl">מעבר לביצוע ה־</span>Discovery <span dir="rtl">עצמו, אני רוצה איתגור של הכיוון הקיים</span>.

<span dir="rtl">בפרט</span>:

**<span dir="rtl">האם אנחנו באמת בונים</span> Platform?**

<span dir="rtl">או שאנחנו לוקחים מספר</span> Use Cases <span dir="rtl">ומפתחים עבור כל אחד לוגיקה ייעודית</span>?

**<span dir="rtl">מה באמת משותף</span>?**

<span dir="rtl">אילו</span> Capabilities <span dir="rtl">מופיעות שוב ושוב, ואילו קיימות רק בגלל</span> Use Case <span dir="rtl">יחיד</span>?

**<span dir="rtl">איפה נכון לעצור</span>?**

<span dir="rtl">איזו לוגיקה באמת שייכת ל־</span>Geography <span dir="rtl">ואיזו צריכה להישאר ב־</span>Consumer, <span dir="rtl">במערכת המקצועית או ב־</span>Context & Meaning?

**<span dir="rtl">מה לא צריך לבנות</span>?**

<span dir="rtl">האם קיימת יכולת ארגונית או מוצר קיים שכבר פותרים חלק מהבעיה</span>?

**<span dir="rtl">האם ה־</span>Roadmap <span dir="rtl">הנוכחי נכון</span>?**

<span dir="rtl">או שהוא משקף יותר את הדרך שבה אנחנו מדמיינים</span> Spatial Platform <span dir="rtl">מאשר את סדר הבעיות שהמשתמשים באמת צריכים לפתור</span>?

**<span dir="rtl">האם</span> Q1 <span dir="rtl">מספיק חזק</span>?**

<span dir="rtl">האם ה־</span>Vertical Slice <span dir="rtl">שנבחר באמת מוכיח למה צריך</span> Geography <span dir="rtl">משותף, או שהוא</span> Use Case <span dir="rtl">שאפשר היה לפתור בקלות באינטגרציה נקודתית</span>?

**<span dir="rtl">מה יקרה כשיגיע</span> Use Case <span dir="rtl">שלא הכרנו</span>?**

<span dir="rtl">זה מבחן חשוב במיוחד</span>.

<span dir="rtl">אם כל שאלה חדשה דורשת מאיתנו</span> Feature <span dir="rtl">חדש — עדיין לא בנינו</span> Platform.

<span dir="rtl">אם ניתן לפרק אותה ל־</span>Capabilities <span dir="rtl">שכבר קיימות, ולהוסיף רק את מה שבאמת חדש — אנחנו בכיוון הנכון</span>.

**Discovery Exit Gate**

<span dir="rtl">בסיום העבודה צריך להיות אפשר לענות בצורה ברורה על</span>:

**WHO**  
<span dir="rtl">מי ה־</span>Consumers <span dir="rtl">הראשונים</span>?

**QUESTIONS**  
<span dir="rtl">מהן השאלות המקצועיות שאנחנו רוצים לפתור</span>?

**DATA**  
<span dir="rtl">איזה מידע נדרש ואיפה הוא נמצא</span>?

**CAPABILITIES**  
<span dir="rtl">מה</span> Geography <span dir="rtl">צריך לדעת לעשות כדי לענות עליהן</span>?

**REUSE**  
<span dir="rtl">אילו מהיכולות משותפות ליותר מ־</span>Use Case <span dir="rtl">אחד</span>?

**EXISTING**  
<span dir="rtl">מה כבר קיים ולא צריך לבנות מחדש</span>?

**Q1**  
<span dir="rtl">מהו ה־</span>Vertical Slice <span dir="rtl">הראשון שאנחנו מתחייבים אליו</span>?

**TEXT → SPATIAL**  
<span dir="rtl">מה בדיוק אנחנו רוצים להוכיח</span>?

**ROADMAP**  
<span dir="rtl">מה בכיוון השנתי הקיים נשאר, מה משתנה ומה עדיין לא הוכח</span>?

**PLATFORM TEST**  
<span dir="rtl">אם מחר מגיעה שאלה עסקית חדשה — האם אנחנו יודעים להרכיב עבורה תשובה מהיכולות שכבר זיהינו, או שאנחנו צריכים לבנות עוד "מכונת נקניקיות</span>"?

<span dir="rtl">רק לאחר שיש לנו תשובות מספיק טובות לשאלות האלה נכון לסגור את ה־</span>Committed Scope <span dir="rtl">ולעבור ל־</span>Architecture <span dir="rtl">ול־</span>Delivery Planning.

**19. Getting Started — First Discovery Cycle**

<span dir="rtl">המטרה בשלב הראשון אינה להשלים את כל ה־</span>Discovery, <span dir="rtl">אלא לייצר מספיק</span> Evidence <span dir="rtl">כדי להתחיל לאתגר את הכיוון הקיים</span>.

**<span dir="rtl">בשבוע הראשון</span>**

**1. <span dir="rtl">אסוף את החומר שכבר קיים</span>**

<span dir="rtl">רכז במקום אחד</span>:

- Use Cases <span dir="rtl">ושאלות עסקיות שכבר התקבלו</span>.

- Consumers <span dir="rtl">שהעלו אותם</span>.

- <span dir="rtl">מערכות ומקורות מידע שעלו</span>.

- <span dir="rtl">יכולות</span> GIS <span dir="rtl">קיימות שאנחנו כבר מכירים</span>.

- <span dir="rtl">דוגמאות אמיתיות</span>, Screenshots <span dir="rtl">או</span> Workflows <span dir="rtl">אם קיימים</span>.

<span dir="rtl">אל תנסה עדיין לתעד את כל עולם ה־</span>Geography <span dir="rtl">בארגון</span>.

**2. <span dir="rtl">בחר 5–7 שאלות ראשונות לניתוח</span>**

<span dir="rtl">עדיף לבחור שאלות שונות זו מזו, כדי לבדוק האם למרות השונות קיימים ביניהן</span> Building Blocks <span dir="rtl">משותפים</span>.

<span dir="rtl">לכל שאלה מלא</span>:

| **<span dir="rtl">שדה</span>** | **<span dir="rtl">מה צריך להבין</span>**                                        |
|--------------------------------|---------------------------------------------------------------------------------|
| Business Question              | <span dir="rtl">מה המשתמש באמת מנסה לדעת</span>?                                |
| Consumer                       | <span dir="rtl">מי צריך את התשובה</span>?                                       |
| Workflow                       | <span dir="rtl">מתי ולמה השאלה עולה</span>?                                     |
| Current Solution               | <span dir="rtl">איך עונים עליה היום</span>?                                     |
| Information Needed             | <span dir="rtl">איזה מידע נדרש</span>?                                          |
| Sources                        | <span dir="rtl">איפה המידע נמצא</span>?                                         |
| Spatial Problem                | <span dir="rtl">מה הבעיה המרחבית שמתחת לשאלה</span>?                            |
| Capabilities                   | <span dir="rtl">מה</span> Geography <span dir="rtl">צריך לדעת לעשות</span>?     |
| Existing Capability            | <span dir="rtl">מה כבר קיים היום</span>?                                        |
| Gap                            | <span dir="rtl">מה באמת חסר</span>?                                             |
| Value                          | <span dir="rtl">מה משתפר אם</span> Geography <span dir="rtl">פותר את זה</span>? |

**3. <span dir="rtl">אל תגדיר עדיין</span> Features**

<span dir="rtl">בשלב הראשון לא להפוך שאלות ל־</span>Epics <span dir="rtl">או</span> Features.

<span dir="rtl">לדוגמה</span>:

<span dir="rtl">לא</span>:

**Feature — <span dir="rtl">הצגת אירועים במרחב מבצע</span>.**

<span dir="rtl">אלא</span>:

**Question — <span dir="rtl">מה קרה במרחב של מבצע</span>?**

↓

**Spatial Problem — <span dir="rtl">למצוא מידע בזמן ובמרחב ביחס ל־</span>Context.**

↓

**Capabilities — Context + Discover + Intersect + Time.**

<span dir="rtl">רק לאחר שנראה מספר שאלות יחד נחליט מה נכון לבנות</span>.

**4. <span dir="rtl">צור</span> Capability Map <span dir="rtl">ראשון</span>**

<span dir="rtl">לאחר פירוק 5–7 השאלות, שים את ה־</span>Capabilities <span dir="rtl">שעלו זו לצד זו</span>.

<span dir="rtl">המטרה היא לראות</span>:

- <span dir="rtl">מה חוזר</span>?

- <span dir="rtl">מה ייחודי לשאלה אחת</span>?

- <span dir="rtl">מה כבר קיים</span>?

- <span dir="rtl">מה חסר</span>?

- <span dir="rtl">מה ניתן להרכיב</span>?

- <span dir="rtl">מה בכלל לא צריך להיות בבעלות</span> Geography?

<span dir="rtl">אין צורך שה־</span>Capability Map <span dir="rtl">הראשון יהיה מושלם</span>.

<span dir="rtl">הוא צריך לאפשר דיון</span>.

**5. <span dir="rtl">חזור עם המלצה — לא רק עם מידע</span>**

<span dir="rtl">בסוף ה־</span>Discovery Cycle <span dir="rtl">הראשון אני מצפה לקבל</span>:

**<span dir="rtl">א. 5–7 שאלות עסקיות מפורקות</span>.**

**<span dir="rtl">ב</span>. Capability Map <span dir="rtl">ראשוני</span>.**

**<span dir="rtl">ג. 3–5</span> Capabilities <span dir="rtl">שנראות כרגע כ־</span>Core Candidates.**

**<span dir="rtl">ד. פערים או הנחות במסמך האסטרטגיה שכבר עכשיו נראים חשודים</span>.**

**<span dir="rtl">ה. המלצה אילו משתמשים / שאלות / מערכות צריך לחקור בשלב הבא</span>.**

**<span dir="rtl">ו. עמדה ראשונית האם ה־</span>Q1 Vertical Slice <span dir="rtl">הנוכחי עדיין נראה נכון</span>.**

**<span dir="rtl">איך לעבוד עם המסמך הזה</span>**

<span dir="rtl">המסמך אינו</span> Specification <span dir="rtl">שצריך לממש</span>.

<span dir="rtl">הוא</span> Hypothesis <span dir="rtl">שצריך לבדוק</span>.

<span dir="rtl">במהלך ה־</span>Discovery <span dir="rtl">סמן כל הנחה משמעותית כאחת מארבע</span>:

**VALIDATED** — <span dir="rtl">מצאנו</span> Evidence <span dir="rtl">שתומך בה</span>.

**CHANGED** — <span dir="rtl">הכיוון נכון אבל צריך להשתנות</span>.

**REJECTED** — <span dir="rtl">ה־</span>Evidence <span dir="rtl">מראה שההנחה אינה נכונה</span>.

**OPEN** — <span dir="rtl">עדיין אין מספיק מידע</span>.

<span dir="rtl">המטרה אינה להגיע בסוף ה־</span>Discovery <span dir="rtl">עם מסמך שמאשר את מה שכבר חשבנו</span>.

<span dir="rtl">המטרה היא להגיע עם תמונה טובה יותר מזו שיש לנו היום</span>.
