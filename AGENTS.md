# AGENTS.md

## Geltungsbereich

Diese Anweisungen gelten für das gesamte Verzeichnis, in dem diese Datei liegt, einschließlich aller Unterverzeichnisse. Eine tiefer liegende `AGENTS.md` darf für ihren Teilbaum präzisere Regeln festlegen.

## Auftrag des Repositories

Dieses Repository entwickelt den **CoRT (Code-reviewing Tutor)** als MVP der „New Joiner Ausbildung“.

Trotz des bestehenden Produktnamens führt der Coach keine Code- oder Pull-Request-Reviews durch. Er nutzt guten, funktionalen und häufig KI-generierten Code als Lernmaterial und stellt New Joinern gezielte Verständnisfragen direkt in der IDE, insbesondere in VS Code.

Der Coach soll den Lernenden befähigen, Kontrollfluss, Datenfluss, Verträge, Abstraktionen, Framework-Mechanismen, Tests und Entwurfsentscheidungen selbst zu erklären. Das Ziel ist besseres Codeverständnis, nicht bessere Bewertung oder Veränderung des Codes.

## Verbindliche Quellen

Vor Änderungen am Produktverhalten zuerst lesen:

1. `SKILL.md` – maßgebliche Beschreibung der Coaching-Logik und Ausgabeformate.
2. `references/curriculum.md` – unveränderte Startvorlage der Lernziele und ihrer initialen Verständnistiefe.
3. `.code-reviewing-tutor/curriculum.md` – zur Laufzeit erzeugte, persönliche Lernstandsdatei des Probanden; sie gehört nicht in das Skill-Paket und soll nicht versioniert werden.
4. `agents/openai.yaml` – Metadaten für Darstellung und Aktivierung; keine fachliche Spezifikation.
4. Vorhandene Produkt-, Architektur- und Entscheidungsdokumente im Repository, sofern sie ergänzt werden.

Bei Widersprüchen gelten direkte Nutzer- oder Systemanweisungen vor dieser Datei. Für das Produktverhalten ist `SKILL.md` die fachliche Quelle der Wahrheit, solange keine ausdrücklich dokumentierte Produktentscheidung sie ersetzt.

## Nicht verhandelbare Produktentscheidungen

- Vorhandenen, funktionalen Code als Lernmaterial behandeln.
- Standardmäßig davon ausgehen, dass KI-generierter Code korrekt und angemessen ist.
- Keine Pull-Request-Reviews oder PR-Kommentare erstellen.
- Keine Gesamteinschätzung, Qualitätsbewertung, Merge-Empfehlung oder Produktionsfreigabe abgeben.
- Nicht systematisch nach Fehlern, Schwachstellen, Risiken oder Code Smells suchen.
- Keine Findings, Schweregrade oder Beanstandungslisten erzeugen.
- Keine ungefragten Refactorings, Verbesserungen oder Ersatzimplementierungen vorschlagen.
- Die IDE, vor allem VS Code, als primäre Produktoberfläche behandeln.
- Genau eine zentrale Verständnisfrage auf einmal stellen.
- Fragen an konkretem Code, Datenfluss, Kontrollfluss, Verträgen oder Framework-Verhalten verankern.
- Relevante Lernziele aus dem persönlichen `.code-reviewing-tutor/curriculum.md` bei der Fragenauswahl bevorzugen, ohne unpassende Lernziele zu erzwingen.
- Die Verständnistiefe je Curriculum-Lernziel nach jeder qualifizierten Antwort monoton fortschreiben.
- Lernziele mit `4/4 – verstanden und übertragen` in späteren Sitzungen nicht mehr behandeln.
- `references/curriculum.md` nur als Startvorlage verwenden und während einer Coaching-Sitzung nicht verändern.
- Im persönlichen Curriculum keine Antworten, Codeausschnitte, Kundendaten oder Gesprächsverläufe speichern.
- Intrinsische Lernmotivation voraussetzen; keine Anti-Cheating-Mechanismen einbauen.
- Annahmen und fehlenden Kontext sichtbar kennzeichnen.

Nicht ohne neue Produktentscheidung in den MVP aufnehmen:

- Planungs- oder Architekturcoach,
- Implementierungs- oder Denkpartner für die initiale Lösung,
- allgemeiner Debugging-Coach,
- Code- oder Pull-Request-Reviewer,
- Reflexions- oder Karriere-Coach,
- Lernkontrolle durch versteckte Tests, Fallen oder Überwachung.

## Gewünschtes Nutzererlebnis

Bei Änderungen an Prompts, Orchestrierung oder UI diese Regeln erhalten:

- Datei, Symbol und Zeilenbereich möglichst präzise nennen.
- Einen kleinen, zusammenhängenden Codeausschnitt als Lerngegenstand wählen.
- Mit neutralem Kontext und genau einer Verständnisfrage beginnen.
- Fragen zu Verhalten, Datenfluss, Verträgen, Abstraktionen, Framework-Mechanismen oder Tests stellen.
- Passende, noch nicht verstandene Curriculum-Lernziele bei der Auswahl berücksichtigen.
- Die nächste Frage an der nächsthöheren sinnvollen Verständnistiefe ausrichten.
- Nach der Antwort die höchste tatsächlich nachgewiesene Verständnistiefe speichern.
- Gute und funktionale Konstruktionen bewusst als Lerngelegenheiten verwenden.
- Keine Frage nach Fehlern oder Qualitätsurteilen stellen.
- Nach einem ernsthaften Denkversuch konkret einordnen und den Mechanismus erklären.
- Bei Blockade die Frage verkleinern oder direkt erklären.
- Bei ausdrücklichem Wunsch eine direkte Erklärung geben, statt künstlich weiterzufragen.
- Jede Lernschleife optional mit einer kleinen prüfbaren IDE-Aktion abschließen.
- Korrekte Herleitungen konkret bestätigen; bloße Zustimmung nicht pauschal loben.
- Am Ende nur den Lerngewinn zusammenfassen, nicht die Codequalität.

## Entwicklungsgrundsätze

### Änderungen klein und nachvollziehbar halten

- Die kleinste Änderung umsetzen, die den gewünschten Produktnutzen vollständig erreicht.
- Keine unaufgeforderten Abhängigkeitswechsel oder Architekturumbauten durchführen.
- Bestehende Konventionen des Repositories vor persönlichen Präferenzen verwenden.
- Neue Abstraktionen erst einführen, wenn ein konkreter Variations- oder Testbedarf sichtbar ist.

### Fachlogik von Integrationen trennen

Soweit die vorhandene Architektur es zulässt, folgende Verantwortlichkeiten getrennt halten:

- Erfassung von IDE-, Datei- und Git-Kontext,
- Rekonstruktion von Kontroll- und Datenfluss,
- Auswahl eines Lernziels einschließlich Curriculum- und Lernstandsabgleich,
- Erzeugung genau einer Verständnisfrage mit definierter Zielstufe,
- Auswertung und Kalibrierung anhand der Antwort,
- monotone Fortschreibung des persönlichen Lernstands,
- Ausgabeformatierung,
- Anbieter- oder Modellintegration,
- Telemetrie und sonstige Persistenz.

Produktregeln wie „eine Frage auf einmal“, „Curriculum berücksichtigen“ oder „keine Qualitätsbewertung“ nicht in VS-Code-spezifischer UI-Logik verstecken.

### IDE-Nähe bewahren

- VS Code als erste Integration optimieren, ohne die Kernlogik unnötig an einzelne Editor-APIs zu koppeln.
- Fundstellen, Symbole und Quellprovenienz durch die Verarbeitung erhalten.
- Aktionen als überprüfbare IDE-Schritte modellieren, etwa Verwendungen suchen, Definition öffnen, Aufrufer ansehen, Test lesen oder Breakpoint setzen.
- Nicht behaupten, Dateien, Tests oder Befehle geprüft zu haben, wenn das System sie nicht tatsächlich ausgeführt hat.
- Codeänderungen nicht zum Standardergebnis des Coaches machen.

### Sicherheit und Vertraulichkeit

- Quellcode, Kundendaten, Tickets und Lerninhalte als potenziell vertraulich behandeln.
- Nur für die aktuelle Verständnisfrage erforderlichen Kontext verarbeiten oder übertragen.
- Geheimnisse, Tokens, personenbezogene Daten und vollständige Kundendaten nicht protokollieren.
- Bei Telemetrie bevorzugt strukturierte, minimierte und nicht inhaltsbezogene Ereignisse verwenden.
- Die lokale Lernstandsdatei als personenbezogenes Entwicklungsdatum behandeln und nicht ohne ausdrücklichen Zweck teilen oder versionieren.

## Arbeitsablauf für Coding Agents

1. Die nächstgelegene `AGENTS.md`, `SKILL.md`, `references/curriculum.md`, gegebenenfalls `.code-reviewing-tutor/curriculum.md` und relevante Projektdokumentation lesen.
2. Bestehende Architektur, Tests, Skripte und Konventionen untersuchen, bevor neue Muster eingeführt werden.
3. Die betroffene Produktinvariante und den kleinsten sinnvollen Änderungsumfang bestimmen.
4. Implementierung und Tests gemeinsam ändern.
5. Vorhandene Format-, Lint-, Typ-, Unit- und Integrationstests mit den repositoryeigenen Befehlen ausführen.
6. Die Änderung gegen die Produktgrenzen und das IDE-Nutzererlebnis prüfen.
7. Ergebnis, ausgeführte Prüfungen, bekannte Einschränkungen und nicht bearbeitete Punkte knapp dokumentieren.

Keine Befehle, Paketmanager oder Frameworks erfinden. Wenn das Repository noch keine ausführbaren Prüfungen bereitstellt, dies offen benennen und die manuell durchgeführte Verifikation beschreiben.

## Testanforderungen

Neue oder geänderte Fachlogik durch Tests absichern. Je nach Änderung insbesondere folgende Fälle berücksichtigen:

- Verständnisfrage zu gutem und funktionalem Code,
- Frage zu Kontrollfluss oder Datenfluss,
- Frage zu einem Typ- oder Funktionsvertrag,
- Frage zu einer Sprach- oder Framework-Mechanik,
- Initialisierung von `.code-reviewing-tutor/curriculum.md` aus der Vorlage,
- Auswahl eines passenden, noch nicht verstandenen Curriculum-Lernziels,
- Überspringen eines nicht passenden Curriculum-Lernziels,
- Überspringen eines Lernziels mit `4/4`,
- Fortschreibung auf die Zielstufe bei einer korrekten Antwort,
- Fortschreibung nur auf eine belegte niedrigere Stufe bei einer teilweise korrekten Antwort,
- keine Fortschreibung bei falscher Antwort, Blockade oder bloßer Erklärung,
- keine Absenkung eines bereits erreichten Lernstands,
- Speicherung ausschließlich des aggregierten Status ohne Antwort- oder Codeinhalt,
- transparenter Fallback bei fehlendem Schreibzugriff,
- Frage zu einem aussagekräftigen Test,
- genau eine zentrale Frage pro Interaktionsschritt,
- korrekte Einordnung einer richtigen Antwort,
- Hilfestellung bei einer teilweise richtigen oder falschen Antwort,
- Verkleinerung der Frage bei Blockade,
- direkte Erklärung auf ausdrücklichen Wunsch,
- präzise Datei- und Zeilenreferenzen,
- keine Finding-, Schweregrad- oder Qualitätsausgabe,
- keine PR- oder Merge-Bewertung,
- keine ungefragte Codeänderung,
- fehlender oder unvollständiger Kontext,
- Schutz vertraulicher Inhalte in Logs oder Telemetrie.

Tests nicht nur auf exakte Modellformulierungen ausrichten. Bevorzugt überprüfbare Strukturen, Zustandsübergänge, Ausschlussregeln und Sicherheitsgrenzen testen.

## Dokumentationsregeln

- Änderungen am fachlichen Verhalten in `SKILL.md` nachführen.
- Lernziele ausschließlich als Stichpunkte in Satzform in `references/curriculum.md` pflegen und mit `Verständnistiefe: **0/4 – unbearbeitet**.` initialisieren.
- Die Laufzeitdatei `.code-reviewing-tutor/curriculum.md` hat dasselbe Format, wird aber pro Proband lokal fortgeschrieben und nicht in das Skill-Paket aufgenommen.
- Änderungen an Darstellung oder Aktivierung in `agents/openai.yaml` nachführen.
- Architekturentscheidungen mit langfristiger Wirkung in einem passenden Entscheidungsdokument festhalten, sobald eine solche Struktur im Repository existiert.
- Beispiele klein, realistisch und frei von Kunden- oder Produktionsdaten halten.
- Bestehende Sprache und Terminologie eines Dokuments beibehalten.

## Definition of Done

Eine Änderung ist erst abgeschlossen, wenn:

- sie innerhalb des verständnisorientierten MVPs liegt,
- das Verhalten mit `SKILL.md` übereinstimmt oder dort bewusst aktualisiert wurde,
- die Curriculum-Vorlage und der persönliche Lernstand korrekt unterschieden werden,
- Fortschritt nur auf Basis nachgewiesener Verständnistiefe fortgeschrieben wird,
- verstandene Lernziele aus späteren Sitzungen ausgeschlossen werden,
- relevante Tests ergänzt oder angepasst wurden,
- verfügbare Qualitätsprüfungen erfolgreich ausgeführt wurden,
- keine Review-, Finding-, Merge- oder Gesamtbewertung eingeführt wurde,
- keine vertraulichen Daten oder unbelegten Erfolgsbehauptungen eingeführt wurden,
- IDE-Nutzbarkeit und konkrete Quellreferenzen erhalten bleiben,
- bekannte Einschränkungen dokumentiert sind.

## Pull-Request-Zusammenfassung für Repository-Änderungen

Bei einem Pull Request an diesem Repository knapp angeben:

- welches Nutzer- oder Lernproblem gelöst wird,
- welche sichtbare Verhaltensänderung entsteht,
- welche Tests und Prüfungen ausgeführt wurden,
- welche Risiken oder Annahmen verbleiben,
- welche bewusst nicht umgesetzten Themen außerhalb des MVPs liegen.

Diese Regel betrifft die Entwicklung des Produkts. Sie bedeutet nicht, dass das Produkt selbst Pull Requests von Nutzern reviewt.
