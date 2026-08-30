**Operational Data Foundation**

**Annual Product Initiative — Operations & Geography**

**1. Initiative**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לבנות בסיס מידע מבצעי ארגוני שמאפשר לעבור ממידע מפוזר במערכות מקצועיות ל־**תמונת מבצעים אחודה, מקושרת, מועשרת בהקשר מרחבי, עדכנית ואמינה**</span>.

<span dir="rtl">בסוף המהלך, צרכנים ארגוניים לא יצטרכו להכיר את כלל מערכות המקור או לבצע אינטגרציות עצמאיות אליהן כדי להבין מבצע ואת ההקשר שלו</span>.

<span dir="rtl">ההתפתחות השנתית</span>:

**Operation → Connected Operation → Contextualized Operation → Trusted & Changing Operational Picture**

**<span dir="rtl">עקרונות מנחים</span>**

- <span dir="rtl">מערכות המקור המקצועיות נשארות</span> Source of Truth <span dir="rtl">בתחומן</span>.

- <span dir="rtl">אין להזין מחדש מידע שכבר קיים במקור מוסמך</span>.

- Operation <span dir="rtl">משמש כ־</span>Context Anchor <span dir="rtl">ולא כמערכת מקצועית חלופית</span>.

- <span dir="rtl">איחוד מידע אינו מבטל</span> Provenance <span dir="rtl">או</span> Ownership.

- <span dir="rtl">לא מבצעים</span> Last Write Wins <span dir="rtl">ללא מדיניות בעלות מוגדרת</span>.

- Source Facts <span dir="rtl">ו־</span>Derived Facts <span dir="rtl">נשמרים כמושגים נפרדים</span>.

- Geography <span dir="rtl">מספק הקשר מרחבי</span>.

- Operations <span dir="rtl">מספק הקשר מבצעי</span>.

- Context & Meaning <span dir="rtl">אחראי ליצירת משמעות מעל המידע</span>.

- Consumers <span dir="rtl">אינם אמורים לבנות מחדש אינטגרציה לכל</span> Source System.

**2. Q1 — Operation Foundation**

**Outcome**

**<span dir="rtl">אנחנו יודעים מהו המבצע</span>.**

<span dir="rtl">בסיום הרבעון, מבצע המופיע במספר מקורות מיוצג כישות מבצעית ארגונית אחת, בעלת</span> Operation Core, <span dir="rtl">מקור ובעלות ברורים, המתעדכנת לאורך זמן וזמינה לצריכה</span>.

**Q1.1 — Operation Source Onboarding**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לחבר את מקורות המידע הראשונים הנדרשים ליצירת תמונת מבצעים ארגונית</span>.

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">לבחור את מערכות המקור הראשונות המכילות מידע על מבצעים</span>.

- <span dir="rtl">למפות אילו מבצעים קיימים בכל מקור</span>.

- <span dir="rtl">למפות אילו שדות קיימים בכל מקור</span>.

- <span dir="rtl">לזהות</span> Source Entity ID.

- <span dir="rtl">להגדיר בעלות על המידע</span>.

- <span dir="rtl">להבין כיצד ומתי המידע משתנה</span>.

- <span dir="rtl">להגדיר ציפיית עדכניות</span>.

- <span dir="rtl">לאפשר קליטת מבצעים מהמקורות שנבחרו</span>.

- <span dir="rtl">לשמר</span> Source + Source Entity ID <span dir="rtl">עבור כל מידע שנקלט</span>.

**Acceptance Criteria**

- <span dir="rtl">מקורות המידע שנבחרו ל־</span>Scope <span dir="rtl">מחוברים</span>.

- <span dir="rtl">ניתן לקלוט מבצע אמיתי מכל</span> Source.

- <span dir="rtl">ניתן לזהות עבור כל</span> Record <span dir="rtl">את מקורו ואת ה־</span>Source Entity ID <span dir="rtl">שלו</span>.

- <span dir="rtl">קיים מיפוי מתועד של המידע והבעלות בכל</span> Source.

**Definition of Done**

<span dir="rtl">ניתן להציג מבצע אמיתי כפי שהתקבל מכל אחד מהמקורות ולשחזר מאיזו מערכת ומאיזו ישות מקורית הגיע</span>.

**Q1.2 — Canonical Operation**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לייצר ייצוג ארגוני משותף למבצע שאינו תלוי במבנה של מערכת מקור מסוימת</span>.

**Operation Core**

- Name

- Time

- Location

- Responsible HQ

- Executing Force

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">להגדיר ייצוג משותף למבצע</span>.

- <span dir="rtl">למפות מידע מכל</span> Source <span dir="rtl">ל־</span>Operation Core.

- <span dir="rtl">לתמוך במידע חלקי כאשר מקור אינו מכיל את כלל ה־</span>Core.

- <span dir="rtl">לשמר</span> Provenance <span dir="rtl">עבור המידע המרכיב את המבצע</span>.

- <span dir="rtl">לאפשר הרחבה עתידית של המבצע מבלי לשנות את ה־</span>Core.

**Acceptance Criteria**

- <span dir="rtl">מבצע מכל אחד ממקורות ה־</span>Scope <span dir="rtl">ניתן לייצוג באותו מבנה ארגוני</span>.

- <span dir="rtl">ניתן לדעת עבור כל שדה מה מקורו</span>.

- <span dir="rtl">היעדר שדה במקור אינו גורם לאובדן יתר המידע</span>.

- <span dir="rtl">המבנה הקנוני אינו תלוי ב־</span>Schema <span dir="rtl">של</span> Source <span dir="rtl">ספציפי</span>.

**Definition of Done**

<span dir="rtl">מבצעים ממערכות שונות ניתנים לצריכה באמצעות אותו ייצוג ארגוני</span>.

**Q1.3 — Cross-Source Operation Identity**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לזהות מתי מידע ממספר מערכות מתייחס לאותו מבצע ולמנוע יצירת תמונות מבצע כפולות</span>.

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">לזהות אותו מבצע בין מקורות</span>.

- <span dir="rtl">לקשר</span> Source IDs <span dir="rtl">לזהות מבצע ארגונית אחת</span>.

- <span dir="rtl">לשמר את כלל הזהויות המקוריות</span>.

- <span dir="rtl">לטפל במקרים שבהם הזיהוי אינו חד־משמעי</span>.

- <span dir="rtl">למנוע</span> Merge <span dir="rtl">אוטומטי כאשר קיימת עמימות מהותית</span>.

**Acceptance Criteria**

- <span dir="rtl">אותו מבצע ממספר מקורות מיוצג כישות ארגונית אחת</span>.

- Source IDs <span dir="rtl">המקוריים נשמרים</span>.

- <span dir="rtl">מידע ממספר מקורות יכול להשלים את אותה ישות</span>.

- <span dir="rtl">מקרה שאינו ניתן לזיהוי בביטחון אינו הופך בשקט ל־</span>Merge <span dir="rtl">שגוי</span>.

**Definition of Done**

<span dir="rtl">נבחר מבצע אמיתי המופיע ביותר ממקור אחד ומוכח כי קיימת עבורו ישות מבצעית ארגונית אחת</span>.

**Q1.4 — Operation Ownership & Continuous Update**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לשמור את תמונת המבצע עדכנית לאורך זמן תוך שמירת בעלות ומקור המידע</span>.

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">להגדיר בעלות עבור שדות שבהם קיימים מספר מקורות</span>.

- <span dir="rtl">לעדכן ישות קיימת בעקבות שינוי במקור</span>.

- <span dir="rtl">למנוע</span> Last Write Wins <span dir="rtl">לא מבוקר</span>.

- <span dir="rtl">לשמר את זהות המבצע לאורך השינוי</span>.

- <span dir="rtl">לזהות</span> Conflict <span dir="rtl">כאשר אין אפשרות להכריע לפי</span> Policy.

- <span dir="rtl">להנגיש את תמונת המבצע לצרכן ראשון</span>.

**Acceptance Criteria**

- <span dir="rtl">שינוי במקור מעדכן את אותו</span> Operation.

- <span dir="rtl">לא נוצרת ישות חדשה בעקבות שינוי</span>.

- <span dir="rtl">ניתן לדעת מה מקור הערך הנוכחי</span>.

- <span dir="rtl">במקרה של מקורות סותרים קיימת מדיניות הכרעה או</span> Conflict <span dir="rtl">גלוי</span>.

- Consumer <span dir="rtl">ראשון מקבל את התמונה המעודכנת</span>.

**Definition of Done**

<span dir="rtl">שינוי אמיתי במערכת מקור עובר</span> End-to-End <span dir="rtl">ומופיע אצל הצרכן באותה ישות מבצע</span>.

**Q1 Exit Scenario**

**Source A + Source B  
→ One Operation  
→ Operation Core  
→ Provenance & Ownership  
→ Source Change  
→ Same Operation Updated  
→ Consumer**

**3. Q2 — Connected Operational Context**

**Outcome**

**<span dir="rtl">אנחנו יודעים מה קשור למבצע</span>.**

Operation <span dir="rtl">הופך מרשומה עצמאית ל־</span>Context Anchor <span dir="rtl">שמאפשר לחבר אליו מידע מבצעי ממערכות מקצועיות שונות</span>.

**Q2.1 — Activities Context**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לחבר פעילויות ממערכות מקצועיות למבצע הארגוני</span>.

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">לקלוט</span> Activities <span dir="rtl">ממקורות נבחרים</span>.

- <span dir="rtl">לזהות לאיזה</span> Operation <span dir="rtl">הן שייכות</span>.

- <span dir="rtl">לשמר</span> Source, Source ID, Ownership <span dir="rtl">וזמן</span>.

- <span dir="rtl">לעדכן</span> Activity <span dir="rtl">כאשר היא משתנה במקור</span>.

- <span dir="rtl">למנוע שכפול</span> Activity <span dir="rtl">רק לצורך הצגתה תחת</span> Operation.

**Acceptance Criteria**

- <span dir="rtl">ניתן לקבל את הפעילויות השייכות למבצע</span>.

- Activity <span dir="rtl">אינה מאבדת את זהותה המקורית</span>.

- <span dir="rtl">מקור ובעלות נשמרים</span>.

- <span dir="rtl">שינוי</span> Activity <span dir="rtl">במקור מתבטא בהקשר המבצע</span>.

- Operations <span dir="rtl">אינו הופך ל־</span>SoT <span dir="rtl">של</span> Activity <span dir="rtl">שבבעלות מערכת אחרת</span>.

**Definition of Done**

<span dir="rtl">מבצע אמיתי זמין לצריכה יחד עם</span> Activities <span dir="rtl">שהגיעו ממערכת מקצועית חיצונית</span>.

**Q2.2 — Operation Relationships**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לאפשר להבין קשרים עסקיים בין מבצעים ולא להתייחס לכל</span> Operation <span dir="rtl">כישות מבודדת</span>.

**Scope <span dir="rtl">ראשוני</span>**

- belongs-to

- related-to

- parent/child

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">לקלוט</span> Relationships <span dir="rtl">המוגדרים במערכות המקור</span>.

- <span dir="rtl">לייצג קשרים באופן אחיד</span>.

- <span dir="rtl">להבחין בין קשר שהגיע ממקור לבין קשר שנגזר במערכת</span>.

- <span dir="rtl">לשמר</span> Provenance <span dir="rtl">של</span> Relationship.

- <span dir="rtl">לאפשר לקשר להשתנות לאורך זמן</span>.

**Acceptance Criteria**

- <span dir="rtl">ניתן לעבור ממבצע למבצעים הקשורים אליו</span>.

- <span dir="rtl">סוג הקשר ברור</span>.

- <span dir="rtl">מקור הקשר ידוע</span>.

- Derived Relationship <span dir="rtl">מסומן ככזה</span>.

- <span dir="rtl">שינוי בקשר אינו מחייב יצירת</span> Operation <span dir="rtl">חדש</span>.

**Definition of Done**

<span dir="rtl">תרחיש אמיתי הכולל מספר מבצעים וקשרים ביניהם ניתן לצריכה</span> End-to-End.

**Q2.3 — Force Context**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לחבר למבצע את המסגרות והכוחות הרלוונטיים מבלי לשכפל את עולם ניהול הכוחות</span>.

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">לקשר</span> Executing Force <span dir="rtl">וישויות כוח נוספות ל־</span>Operation.

- <span dir="rtl">לשמר</span> Reference <span dir="rtl">לישות המקצועית</span>.

- <span dir="rtl">לאפשר שינוי בכוח במקור להתבטא בהקשר המבצע</span>.

- <span dir="rtl">להגדיר את גבול האחריות בין</span> Operations <span dir="rtl">לבין מערכת המקור של הכוח</span>.

**Acceptance Criteria**

- <span dir="rtl">ניתן לדעת אילו כוחות קשורים למבצע</span>.

- <span dir="rtl">ניתן לזהות את ישות הכוח המקורית</span>.

- Operations <span dir="rtl">אינו מנהל את המידע המקצועי של הכוח</span>.

- <span dir="rtl">שינוי רלוונטי במקור יכול לעדכן את</span> Context <span dir="rtl">המבצע</span>.

**Definition of Done**

<span dir="rtl">מבצע אמיתי מחובר לכוח ממערכת מקצועית תוך שמירת</span> Ownership <span dir="rtl">ו־</span>Provenance.

**Q2.4 — Milestones & Schedules Context**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לחבר למבצע אבני דרך ולוחות זמנים הנמצאים במערכות מקצועיות שונות</span>.

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">לקלוט</span> Milestones <span dir="rtl">ו־</span>Schedules <span dir="rtl">רלוונטיים</span>.

- <span dir="rtl">לקשר אותם ל־</span>Operation.

- <span dir="rtl">לשמר זמן, מקור ובעלות</span>.

- <span dir="rtl">לתמוך בעדכון כאשר לוח הזמנים משתנה</span>.

- <span dir="rtl">למנוע יצירת מקור אמת מקביל עבור לוחות הזמנים</span>.

**Acceptance Criteria**

- <span dir="rtl">ניתן לקבל עבור מבצע את אבני הדרך ולוחות הזמנים הרלוונטיים</span>.

- <span dir="rtl">מקור כל פריט נשמר</span>.

- <span dir="rtl">שינוי במקור מתבטא בתמונה</span>.

- <span dir="rtl">אין צורך לנהל מחדש את לוח הזמנים ב־</span>Operations.

**Definition of Done**

Operation <span dir="rtl">אמיתי כולל</span> Context <span dir="rtl">של</span> Activities, Forces, Related Operations <span dir="rtl">ו־</span>Milestones/Schedules <span dir="rtl">ממקורות מקצועיים</span>.

**Q2 Exit Scenario**

\*\*Operation

- Activities

- Forces

- Related Operations

- Milestones / Schedules  
  → Connected Operational Context\*\*

**4. Q3 — Geo-Operational Context**

**Outcome**

**<span dir="rtl">אנחנו יודעים איפה המבצע ומה רלוונטי אליו במרחב</span>.**

<span dir="rtl">המבצע מחובר להקשר הגיאוגרפי שלו באופן שמאפשר לצרכן להבין את המרחב בלי להכיר את כלל מערכות ושכבות ה־</span>GIS.

**Q3.1 — Geographic Source Onboarding**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לייצר בסיס גיאוגרפי ארגוני ממקורות מוסמכים לצורך יצירת</span> Context <span dir="rtl">מרחבי</span>.

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">לבחור</span> Geo Domains <span dir="rtl">ראשונים</span>.

- <span dir="rtl">להגדיר</span> Source of Truth <span dir="rtl">לכל</span> Domain.

- <span dir="rtl">לקלוט ישויות וגיאומטריות</span>.

- <span dir="rtl">לשמר</span> Source ID.

- <span dir="rtl">לשמר</span> Ownership.

- <span dir="rtl">להגדיר</span> Freshness expectation.

- <span dir="rtl">לייצר זהות עקבית לישות גיאוגרפית</span>.

**Acceptance Criteria**

- Geo Domains <span dir="rtl">שנבחרו זמינים לצריכה</span>.

- <span dir="rtl">לכל ישות קיימים</span> Geometry, Identity <span dir="rtl">ו־</span>Source.

- <span dir="rtl">ניתן לדעת מי בעל המידע</span>.

- <span dir="rtl">עדכון מהמקור יכול לעדכן את הישות</span>.

**Definition of Done**

<span dir="rtl">ישויות גיאוגרפיות אמיתיות ממספר</span> Domains <span dir="rtl">זמינות לצריכה בצורה עקבית</span>.

**Q3.2 — Operation ↔ Geography Linking**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לחבר מבצע לישויות הגיאוגרפיות הרלוונטיות אליו</span>.

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">להשתמש במיקום או בגיאומטריה של המבצע</span>.

- <span dir="rtl">לזהות</span> Geo Entities <span dir="rtl">רלוונטיים</span>.

- <span dir="rtl">לייצר קשר בין</span> Operation <span dir="rtl">לבין</span> Geography.

- <span dir="rtl">לשמר כיצד נוצר הקשר</span>.

- <span dir="rtl">להבחין בין קשר שהגיע ממקור לבין קשר שנגזר מחישוב</span>.

**Acceptance Criteria**

- <span dir="rtl">ניתן לקבל</span> Geographic Context <span dir="rtl">עבור</span> Operation.

- <span dir="rtl">החיבור אינו מחייב את הצרכן להכיר את מערכת ה־</span>GIS <span dir="rtl">המקורית</span>.

- <span dir="rtl">ניתן להבחין בין</span> Location <span dir="rtl">שהגיע ממקור לבין</span> Geographic Relationship <span dir="rtl">שנגזר ממנו</span>.

- <span dir="rtl">מקור הישויות הגיאוגרפיות נשמר</span>.

**Definition of Done**

<span dir="rtl">מבצע אמיתי מחובר למספר סוגים של</span> Geo Entities <span dir="rtl">רלוונטיים</span>.

**Q3.3 — Spatial Relationships**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">להפוך מיקום וגיאומטריה ליחסים מרחביים הניתנים לצריכה עסקית</span>.

**Scope <span dir="rtl">ראשוני</span>**

- inside

- intersects

- near

- overlaps

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">לחשב יחסים מרחביים בין</span> Operation <span dir="rtl">ל־</span>Geo Entities.

- <span dir="rtl">לשמר שהקשר הוא</span> Derived Fact.

- <span dir="rtl">לקשר את התוצאה לישויות שעל בסיסן חושבה</span>.

- <span dir="rtl">לאפשר לצרכן לקבל</span> Relationship <span dir="rtl">מובנה ולא רק</span> Geometry.

**Acceptance Criteria**

- Spatial Relationships <span dir="rtl">שנבחרו ל־</span>Scope <span dir="rtl">נתמכים</span>.

- <span dir="rtl">כל</span> Relationship <span dir="rtl">מקושר לישויות שעל בסיסן חושב</span>.

- Derived Fact <span dir="rtl">אינו מוצג כמידע שהגיע ממערכת מקור</span>.

- <span dir="rtl">ניתן להסביר כיצד נוצר הקשר</span>.

**Definition of Done**

<span dir="rtl">עבור מבצע אמיתי ניתן לענות בצורה מובנית אילו ישויות נמצאות בתוכו, חופפות לו, מצטלבות איתו או נמצאות בקרבתו</span>.

**Q3.4 — Dynamic Geographic Context**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">להבטיח שההקשר הגיאוגרפי של המבצע נשאר נכון כאשר המבצע או המרחב משתנים</span>.

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">לזהות שינוי במיקום או בגיאומטריה של</span> Operation.

- <span dir="rtl">לזהות שינוי ב־</span>Geo Entity <span dir="rtl">רלוונטית</span>.

- <span dir="rtl">להעריך מחדש</span> Relationships <span dir="rtl">מושפעים</span>.

- <span dir="rtl">לעדכן את ה־</span>Geo Context.

- <span dir="rtl">להנגיש את התמונה המעודכנת לצרכנים</span>.

**Acceptance Criteria**

- <span dir="rtl">שינוי במיקום מבצע גורר הערכה מחדש של ההקשר</span>.

- <span dir="rtl">שינוי ב־</span>Geo Entity <span dir="rtl">יכול להשפיע על</span> Operations <span dir="rtl">רלוונטיים</span>.

- <span dir="rtl">קשר שאינו תקף עוד אינו ממשיך להופיע כעובדה עדכנית</span>.

- Provenance <span dir="rtl">נשמר לאחר חישוב מחדש</span>.

**Definition of Done**

<span dir="rtl">שינוי אמיתי במבצע או בגיאוגרפיה משנה את ה־</span>Geo Context <span dir="rtl">המוצג לצרכן ללא הזנה ידנית</span>.

**Q3 Exit Scenario**

\*\*Operation

- Geographic Sources  
  → Relevant Geo Entities  
  → Spatial Relationships  
  → Geographic Context  
  → Operation / Geography Change  
  → Updated Context\*\*

**5. Q4 — Trusted & Changing Operational Picture**

**Outcome**

**<span dir="rtl">אנחנו יודעים מה השתנה ועל איזה מידע ניתן לסמוך</span>.**

<span dir="rtl">תמונת המבצע עוברת מ־</span>Current Snapshot <span dir="rtl">ל־</span>Trusted, Temporal Operational Context.

**Q4.1 — Operational Change Detection**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לאפשר לצרכנים להבין מה השתנה בתמונת המבצע ולא רק לקבל</span> Snapshot <span dir="rtl">חדש</span>.

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">לזהות שינויים ב־</span>Operation Core.

- <span dir="rtl">לזהות שינויים ב־</span>Relationships.

- <span dir="rtl">לזהות שינויים ב־</span>Activities <span dir="rtl">וב־</span>Operational Context.

- <span dir="rtl">לזהות שינויים ב־</span>Geographic Context.

- <span dir="rtl">לשמר</span> Previous Value <span dir="rtl">ו־</span>Current Value.

- <span dir="rtl">לקשר שינוי למקור ולזמן</span>.

- <span dir="rtl">להבחין בין שינוי טכני לבין שינוי בעל משמעות עסקית</span>.

**Acceptance Criteria**

- <span dir="rtl">ניתן לזהות אילו פרטים השתנו</span>.

- <span dir="rtl">ניתן לדעת מה היה הערך הקודם ומה הערך החדש</span>.

- <span dir="rtl">מקור השינוי ידוע</span>.

- <span dir="rtl">זמן השינוי ידוע</span>.

- <span dir="rtl">עדכון טכני בלבד אינו חייב להפוך ל־</span>Business Change.

**Definition of Done**

<span dir="rtl">שינוי משמעותי במבצע אמיתי ניתן לצריכה כ־</span>Change <span dir="rtl">ולא רק כמצב חדש</span>.

**Q4.2 — History & Temporal State**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לאפשר להבין מה הייתה תמונת המבצע בנקודת זמן קודמת</span>.

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">לשמר היסטוריית שינויים רלוונטית</span>.

- <span dir="rtl">לאפשר שחזור מצב</span> Operation <span dir="rtl">לאורך זמן</span>.

- <span dir="rtl">לשמר היסטוריה של</span> Relationships <span dir="rtl">ו־</span>Context <span dir="rtl">כאשר נדרש</span>.

- <span dir="rtl">להבחין בין</span>:

  - Event Time

  - Source Update Time

  - Ingestion Time

**Acceptance Criteria**

- <span dir="rtl">ניתן לקבל</span> Current State.

- <span dir="rtl">ניתן לקבל</span> Previous State.

- <span dir="rtl">ניתן להבין מתי התרחש שינוי</span>.

- <span dir="rtl">עדכון אינו מוחק את המידע שהיה ידוע קודם</span>.

**Definition of Done**

<span dir="rtl">עבור מבצע אמיתי ניתן להציג מספר גרסאות של התמונה ולהסביר את ההבדלים ביניהן</span>.

**Q4.3 — Trust, Freshness & Conflict**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לאפשר לצרכן להבין עד כמה המידע שעליו הוא מסתמך עדכני ואמין</span>.

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">להנגיש</span> Source.

- <span dir="rtl">להנגיש</span> Ownership.

- <span dir="rtl">להנגיש זמן עדכון</span>.

- <span dir="rtl">לזהות מידע שהתיישן ביחס לציפיית העדכניות שלו</span>.

- <span dir="rtl">לזהות סתירה בין מקורות</span>.

- <span dir="rtl">להימנע מהכרעה סמויה כאשר אין</span> Policy <span dir="rtl">מוסכם</span>.

- <span dir="rtl">להבחין בין</span> Source Fact <span dir="rtl">לבין</span> Derived Fact.

**Acceptance Criteria**

- <span dir="rtl">ניתן לדעת מקור ועדכניות של מידע מרכזי</span>.

- <span dir="rtl">ניתן לזהות</span> Stale Information.

- Conflict <span dir="rtl">בין מקורות ניתן לזיהוי</span>.

- Conflict <span dir="rtl">אינו נפתר אוטומטית ללא</span> Policy.

- <span dir="rtl">ניתן לזהות</span> Derived Information.

**Definition of Done**

<span dir="rtl">עבור</span> Operation <span dir="rtl">אמיתי ניתן להסביר</span>:

**<span dir="rtl">מה אנחנו יודעים → מאיפה אנחנו יודעים → ממתי אנחנו יודעים → מי בעל המידע → האם קיימת סתירה</span>.**

**Q4.4 — Context Distribution & Consumption**

**<span dir="rtl">מטרה</span>**

<span dir="rtl">לאפשר למוצרים ולשכבות חכמות לצרוך</span> Context <span dir="rtl">מבצעי אמין ללא אינטגרציה עצמאית לכל מקורות המידע</span>.

**Context Package**

<span dir="rtl">ה־</span>Context <span dir="rtl">הניתן לצריכה עשוי לכלול</span>:

- Operation Core

- Activities

- Operation Relationships

- Forces

- Milestones & Schedules

- Geographic Context

- Provenance

- Ownership

- Freshness

- Conflicts

- Changes

**Consumers**

<span dir="rtl">בין הצרכנים האפשריים</span>:

- Zira / <span dir="rtl">מודול ניהול מבצעים</span>

- Commander Space

- Context & Meaning

- Agents

- <span dir="rtl">מוצרים ארגוניים נוספים</span>

**<span dir="rtl">עשייה</span>**

- <span dir="rtl">לאפשר לצרכנים לקבל</span> Context <span dir="rtl">מבצעי משותף</span>.

- <span dir="rtl">לאפשר קבלת</span> Current State.

- <span dir="rtl">לאפשר קבלת</span> Changes <span dir="rtl">רלוונטיים</span>.

- <span dir="rtl">למנוע צורך באינטגרציה עצמאית לכל</span> Source.

- <span dir="rtl">לאפשר ל־</span>Context & Meaning <span dir="rtl">ול־</span>Agents <span dir="rtl">לצרוך</span> Context <span dir="rtl">מובנה הכולל</span> Trust Metadata.

**Acceptance Criteria**

- Consumers <span dir="rtl">שנבחרו ל־</span>Scope <span dir="rtl">צורכים את אותו בסיס</span> Context.

- Consumer <span dir="rtl">אינו נדרש להתחבר למערכות המקור עבור מידע שכבר מסופק</span>.

- <span dir="rtl">שינוי רלוונטי יכול להגיע לצרכן</span>.

- Context & Meaning <span dir="rtl">יכול לקבל</span> Context <span dir="rtl">מובנה</span>.

- Provenance <span dir="rtl">ו־</span>Freshness <span dir="rtl">אינם אובדים בדרך לצרכן</span>.

**Definition of Done**

<span dir="rtl">אותו</span> Operation <span dir="rtl">וה־</span>Context <span dir="rtl">שלו נצרכים על ידי מספר מוצרים או שירותים ללא בניית</span> Data Pipeline <span dir="rtl">עצמאי עבור כל</span> Consumer.

**6. Year-End Acceptance Scenario**

<span dir="rtl">בסוף השנה יש לבחור מבצע אמיתי ולהציג תרחיש</span> End-to-End <span dir="rtl">מלא</span>.

**Step 1 — Sources**

<span dir="rtl">מספר מערכות מקצועיות מחזיקות מידע על אותו מבצע</span>.

**Step 2 — Identity**

<span dir="rtl">המידע מזוהה כ־</span>Operation <span dir="rtl">ארגוני אחד</span>.

**Step 3 — Core**

<span dir="rtl">נבנה</span> Operation Core <span dir="rtl">אחוד</span>.

**Step 4 — Operational Context**

<span dir="rtl">מחוברים</span> Activities, Forces, Related Operations <span dir="rtl">ו־</span>Milestones/Schedules.

**Step 5 — Geographic Context**

<span dir="rtl">המבצע מחובר לישויות וליחסים המרחביים הרלוונטיים אליו</span>.

**Step 6 — Change**

<span dir="rtl">מידע באחד המקורות משתנה</span>.

**Step 7 — Continuous Update**

<span dir="rtl">אותה ישות מתעדכנת ללא יצירת כפילות</span>.

**Step 8 — History**

<span dir="rtl">המצב הקודם נשמר</span>.

**Step 9 — Trust**

<span dir="rtl">ניתן לדעת מה השתנה, מה מקור המידע, מי בעליו, מתי עודכן והאם קיימת סתירה</span>.

**Step 10 — Consumption**

<span dir="rtl">ה־</span>Context <span dir="rtl">המעודכן זמין לצרכנים הארגוניים</span>.

**Step 11 — Meaning**

Context & Meaning / Agents <span dir="rtl">יכולים לצרוך את התמונה האמינה והמובנית לצורך יצירת משמעות ותוצרים</span>.

**7. Annual Definition of Done**

<span dir="rtl">ה־</span>Initiative <span dir="rtl">מסתיים כאשר הארגון מסוגל לעבור מ</span>:

**<span dir="rtl">מידע על מבצעים מפוזר בין מערכות מקצועיות</span>**

<span dir="rtl">ל</span>:

**<span dir="rtl">מבצע הוא</span> Context Anchor <span dir="rtl">ארגוני אחד, שמחבר את המידע המבצעי הרלוונטי אליו, ממקם אותו במרחב, מתעדכן לאורך זמן, שומר את מקור ובעלות המידע ומאפשר לצרכנים לקבל תמונה משותפת, עדכנית ואמינה</span>.**

**8. Product Boundaries**

**Operations <span dir="rtl">אחראי על</span>**

- <span dir="rtl">זהות המבצע הארגונית</span>.

- Operation Core.

- <span dir="rtl">חיבור</span> Context <span dir="rtl">מבצעי למבצע</span>.

- Relationships <span dir="rtl">בין מבצעים וישויות מבצעיות</span>.

- <span dir="rtl">הנגשת תמונת המבצע האחודה</span>.

**Geography <span dir="rtl">אחראי על</span>**

- <span dir="rtl">זהות וישויות גיאוגרפיות</span>.

- Geometry.

- Geographic Source Integration.

- Spatial Relationships.

- Geographic Context.

**Source Systems <span dir="rtl">אחראיות על</span>**

- <span dir="rtl">המידע המקצועי שבבעלותן</span>.

- <span dir="rtl">יצירה ועדכון של המידע המקצועי</span>.

- <span dir="rtl">איכות המידע במקור בהתאם לאחריותן</span>.

**Context & Meaning <span dir="rtl">אחראי על</span>**

- <span dir="rtl">שילוב</span> Context <span dir="rtl">לצורך הבנת משמעות</span>.

- <span dir="rtl">זיקוק מידע</span>.

- <span dir="rtl">הסקת משמעות מעל</span> Facts.

- <span dir="rtl">יצירת</span> Insights <span dir="rtl">ותוצרים המבוססים על</span> Context.

**Consumers <span dir="rtl">אחראים על</span>**

- <span dir="rtl">אופן הצגת המידע</span>.

- Workflow <span dir="rtl">מקצועי</span>.

- <span dir="rtl">פעולות משתמש</span>.

- <span dir="rtl">החלטות ותהליכים הנבנים מעל ה־</span>Context.

**9. Out of Scope**

<span dir="rtl">ה־</span>Initiative <span dir="rtl">אינו מיועד ל</span>:

- <span dir="rtl">החלפת מערכות מקצועיות קיימות</span>.

- <span dir="rtl">שכפול מלא של כלל המידע ממערכות המקור</span>.

- <span dir="rtl">הפיכת</span> Operations Store <span dir="rtl">או</span> Geography Store <span dir="rtl">ל־</span>Source of Truth <span dir="rtl">של</span> Domains <span dir="rtl">מקצועיים אחרים</span>.

- <span dir="rtl">בניית</span> UI <span dir="rtl">מקצועי לכל</span> Domain.

- <span dir="rtl">יצירת המלצות מבצעיות בתוך</span> Data Pipelines.

- <span dir="rtl">קבלת החלטות אוטונומית</span>.

- <span dir="rtl">פתרון באמצעות</span> Last Write Wins <span dir="rtl">ללא</span> Ownership Policy.

- <span dir="rtl">מחיקת</span> Provenance <span dir="rtl">לצורך יצירת מודל אחוד</span>.

- <span dir="rtl">יצירת</span> Pipeline <span dir="rtl">נפרד עבור כל</span> Consumer.

**10. Jira Hierarchy**

**Initiative**

**Operational Data Foundation**

**Q1 — Operation Foundation**

- Q1.1 Operation Source Onboarding

- Q1.2 Canonical Operation

- Q1.3 Cross-Source Operation Identity

- Q1.4 Operation Ownership & Continuous Update

**Q2 — Connected Operational Context**

- Q2.1 Activities Context

- Q2.2 Operation Relationships

- Q2.3 Force Context

- Q2.4 Milestones & Schedules Context

**Q3 — Geo-Operational Context**

- Q3.1 Geographic Source Onboarding

- Q3.2 Operation ↔ Geography Linking

- Q3.3 Spatial Relationships

- Q3.4 Dynamic Geographic Context

**Q4 — Trusted & Changing Operational Picture**

- Q4.1 Operational Change Detection

- Q4.2 History & Temporal State

- Q4.3 Trust, Freshness & Conflict

- Q4.4 Context Distribution & Consumption

**11. Annual Product Narrative**

**Q1 — Identify**  
<span dir="rtl">אנחנו יודעים **מהו המבצע**</span>.

↓

**Q2 — Connect**  
<span dir="rtl">אנחנו יודעים **מה קשור למבצע**</span>.

↓

**Q3 — Contextualize**  
<span dir="rtl">אנחנו יודעים **איפה המבצע ומה רלוונטי אליו במרחב**</span>.

↓

**Q4 — Understand Change & Trust**  
<span dir="rtl">אנחנו יודעים **מה השתנה ועל איזה מידע ניתן לסמוך**</span>.

**Operation → Connected Operation → Contextualized Operation → Trusted & Changing Operational Picture**
