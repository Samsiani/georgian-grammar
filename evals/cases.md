# Test cases

25 cases for checking the skill by hand, or after any rule change. The expected answers need review by a native speaker before they are treated as gold.

**How to run:** give the model the input with the skill installed. Compare its output with the expected column, then run it again without the skill and compare.

## Correction cases: the text has errors

| ID | Input | Expected correction | Rules |
|---|---|---|---|
| C01 | კომპანია ახალი ტელეფონი გამოუშვა. | კომპანიამ ახალი ტელეფონი გამოუშვა. | VSER-02 |
| C02 | მასწავლებელმა მოსწავლეს დავალებას მისცა. | მასწავლებელმა მოსწავლეს დავალება მისცა. | VSER-02 |
| C03 | სტუმრებმა გვიან მოვიდნენ. | სტუმრები გვიან მოვიდნენ. | VSER-02 |
| C04 | ოთხი სტუდენტები ლექციაზე არ მოვიდნენ. | ოთხი სტუდენტი ლექციაზე არ მოვიდა. | NUM-02, NUM-03 |
| C05 | გუშინ ბევრი საინტერესო ამბები მოხდნენ. | გუშინ ბევრი საინტერესო ამბავი მოხდა. | NUM-02, AGR-01 |
| C06 | ნინო ძალიან უყვარს კლასიკური მუსიკა. | ნინოს ძალიან უყვარს კლასიკური მუსიკა. | VPER-05 |
| C07 | ჩემ მეგობარს დიდს ოთახში ვხვდები. | ჩემს მეგობარს დიდ ოთახში ვხვდები. | PRON-03, ADJ-02 |
| C08 | ეს საჩუქარი დედასთვის ვიყიდე. | ეს საჩუქარი დედისთვის ვიყიდე. | POSTP-02, CASE-05 |
| C09 | სტუმარის ოთახი მეორე სართულზეა. | სტუმრის ოთახი მეორე სართულზეა. | CASE-04 |
| C10 | ეს ნანის წიგნია, გიორგმა მომცა. | ეს ნანას წიგნია, გიორგიმ მომცა. | CASE-08 |
| C11 | ნუ წადი, ჯერ არ დაგვიმთავრებია. | ნუ წახვალ, ჯერ არ დაგვიმთავრებია. (or: არ წახვიდე, …) | VSER-04 |
| C12 | ნინომ თქვა, რომ ხვალ მოვალ. | ნინომ თქვა, რომ ხვალ მოვა. (or: ნინომ თქვა, ხვალ მოვალო.) | SYN-05, SYN-07 |
| C13 | ბატონი გიორგი, თქვენ ხომ იცი, რომ შეხვედრა ხვალ არის? | ბატონო გიორგი, თქვენ ხომ იცით, რომ შეხვედრა ხვალ არის? | REG-02, VPER-07 |
| C14 | სასტუმრო "თბილისი" ქალაქის ცენტრშია, და იქ ყოველთვის ბევრი ტურისტია. | სასტუმრო „თბილისი“ ქალაქის ცენტრშია და იქ ყოველთვის ბევრი ტურისტია. | PUNCT-06, PUNCT-02 |
| C15 | მთავრობის მიერ მიღებულ იქნა გადაწყვეტილება, რომელიც მოსახლეობას დახმარებას აღმოუჩენს. | მთავრობამ მიიღო გადაწყვეტილება, რომელიც მოსახლეობას დაეხმარება. | VOICE-02, STYLE-02 |
| C16 | ილია ჭავჭავაძე XIX-ე საუკუნეში ცხოვრობდა, გიორგი კი 60-ე სკოლაში სწავლობს. | ილია ჭავჭავაძე XIX საუკუნეში ცხოვრობდა, გიორგი კი მე-60 სკოლაში სწავლობს. | NUM-05 |
| C17 | ის ცნობილი ქართული მწერალია და ინგლისულ ენასაც კარგად ფლობს. | ის ცნობილი ქართველი მწერალია და ინგლისურ ენასაც კარგად ფლობს. | ADJ-05, SPELL-02 |
| C18 | დილით მან თავისი კბილები გაიხეხა და თავისი პალტო ჩაიცვა. | დილით მან კბილები გაიხეხა და პალტო ჩაიცვა. | VERS-02 |
## Clean cases: the text is correct and must come back unchanged

| ID | Input | Expected |
|---|---|---|
| K01 | გუშინ ბავშვებმა ეზოში ითამაშეს, მერე სახლში დაბრუნდნენ. | No changes; the model says the text is correct. |
| K02 | თუ ხვალ წვიმა იქნება, სახლში დავრჩებით. | No changes. |
| K03 | ნინოს ორი ძმა ჰყავს, ორივე ექიმია. | No changes. |
| K04 | გამარჯობათ, როგორ ბრძანდებით? | No changes: `გამარჯობათ` is correct for polite `თქვენ` (REG-03). |

## Writing and explanation cases: check against a checklist

| ID | Prompt | The answer must |
|---|---|---|
| G01 | Explain: why `ბავშვმა დაწერა`, but `ბავშვი მოვიდა`? | cite VSER-02; give the `-ეს` / `-ნენ` test; explain transitive vs motion verbs |
| G02 | Translate: "Three students couldn't come to the meeting because they were sick." | use `სამი სტუდენტი` (singular noun), `ვერ მოვიდა` (`ვერ`, singular verb), `რადგან` with a comma before it; no `ერთი`/`ეს` article calques |
| G03 | Write two polite opening sentences of an email to Mr. Davit, asking to meet next Tuesday. | use `პატივცემულო ბატონო დავით,` (vocative, bare stem); `თქვენ` with plural verbs (`შეგიძლიათ`, `გცალიათ`); `მომავალ სამშაბათს` (dative); no calques or filler |
