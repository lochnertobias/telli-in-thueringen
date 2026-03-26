===========================================================================
I. TELLI IN THÜRINGEN
===========================================================================

1) ZIELE DER SEITE
---------------------------------------------------------------------------
- liefert Informationen und Anregungen über den KI-Chatbot „telli“ im schulischen Kontext
- Unterstützung von Lehrkräften durch Promptbeispiele

2) FUNKTIONEN DER SEITE
---------------------------------------------------------------------------
- Bereitstellung von Informationen zu „telli“
- Orientierungshilfen für Lehrkräfte
- Beispiel für Prompts die nach Fächern, telli-Funktionen und Schulstufen gefiltert werden können



===========================================================================
II. IMPRESSUM UND CHANGELOG
===========================================================================
erstellt von Tobias Lochner,
Dr. Sulzberger-Gymnasium, Bad Salzungen, 2026

basierend auf einer Idee von
Martin Kurz, Hessische Lehrkräfteakademie, 2026,  https://mgkurz.github.io/-telli-deutsch-ideen/

Neue Funktionen im Vergleich zur hessischen Vorlage:
Erweiterung der Prompt-Datenbank um die Ebene Fächer
Promptssammlung in json-Dateien ausgelagert (eine json-Datei pro Fach)
Dynamisches Einlesen der Fächer via Inhaltsverzeichnis (faecher.json)



===========================================================================
III.PROMPT-DATENFORMAT DOKUMENTATION
===========================================================================

Dieses Dokument beschreibt die Struktur zur Speicherung von KI-Prompts 
und Lernszenarien im Bildungskontext.

1. DATEISTRUKTUR & ORGANISATION
---------------------------------------------------------------------------
* DATEINAMEN: Fachname als Dateiname (z. B. deutsch.json, mathe.json).
* TAGGING:    Der Dateiname wird beim Einlesen automatisch als Tag genutzt.
* REGISTER:   Alle genutzten Fach-Dateien müssen in der zentralen Datei 
              'faecher.json' eingetragen sein.

2. FELDER DER JSON-OBJEKTE
---------------------------------------------------------------------------
Jeder Eintrag muss exakt diese sieben Felder enthalten:

FELD             | TYP    | BESCHREIBUNG
-----------------+--------+------------------------------------------------
id               | String | Eindeutige Kennzahl (4-stellig, z. B. "0123")
titel            | String | Überschrift des Prompts
fach             | String | Das jeweilige Unterrichtsfach
funktion         | String | Kategorie (z. B. Assistent, Dialogpartner)
stufe            | String | Zielgruppe (Primarstufe, Sek 1, Sek 2)
kurzbeschreibung | String | Zusammenfassung des Inhalts
prompt           | String | Der eigentliche Befehl an die KI
-----------------+--------+------------------------------------------------

3. BEISPIEL EINES EINTRAGS
---------------------------------------------------------------------------
Hier ein Muster für einen korrekten JSON-Datensatz:

{
  "id": "0123",
  "titel": "Sachtext-Analyse-Check",
  "fach": "Deutsch",
  "funktion": "Assistent",
  "stufe": "Sekundarstufe 1",
  "kurzbeschreibung": "Feedback-Tool für Sachtexte, Klasse 8.",
  "prompt": "Du bist ein Schreibcoach. Prüfe den Entwurf auf..."
}

4. VALIDIERUNGSREGELN
---------------------------------------------------------------------------
- IDs müssen immer 4 Zeichen lang sein.
- Das Feld 'fach' sollte identisch mit dem Dateinamen sein.
- Alle Felder sind Pflichtfelder (dürfen nicht fehlen).

5. FAQ
---------------------------------------------------------------------------

5.1 
Q: Wie füge ich ein neues Fach hinzu?
A: 1.) json-Datei mit dem Fachnamen anlegen (z.B. religion.json) und mit Inhalten nach Vorgabe befüllen
   2.) faecher.json Datei um den Eintrag des Faches erweitern

5.2 
Q: Wie kann ich Prompts hinzufügen oder anpassen?
A: Die json-Datei mit dem passenden Fachnamen (z.B. mathematik.json) mit einem Texteditor bearbeiten oder erweitern, dabei die Vorgaben zum Datei-Aufbau (siehe oben) einhalten
   

===========================================================================
Ende der Dokumentation
