# Restaurant Reservierungs-Bot

Mein erstes Projekt mit n8n. Ein Chat-Bot, der Restaurant-Reservierungen 
entgegennimmt und automatisch in den Google Kalender einträgt.

## Was macht der Bot

Man chattet mit dem Bot (über das HTML-Interface), er fragt nach Name, 
Datum, Uhrzeit und Personenanzahl - eine Sache nach der anderen. Sobald 
er alles hat, erstellt er automatisch einen Kalendereintrag und bestätigt 
die Reservierung.

Läuft über einen n8n-Workflow im Hintergrund: Webhook nimmt die Nachrichten 
an, ein LLM (läuft über Groq) übernimmt die Konversation, und wenn alle 
Infos gesammelt wurden, geht es an die Google Calendar API.

## Verwendet

- n8n
- Groq API (openai/gpt-oss-120b)
- Google Calendar API
- HTML/CSS/JS fürs Frontend

## Zum Ausprobieren

Der Workflow (First_Reservation_AI.json) lässt sich in eine eigene 
n8n-Instanz importieren. Braucht dann einen eigenen Groq API-Key und 
eine eigene Google Calendar Verbindung. In der HTML-Datei muss die 
Webhook-URL angepasst werden.

## Was noch nicht so gut ist

- Kein Check, ob der Termin überhaupt frei ist - der Bot bucht einfach drauf los
- Die Antwort der KI wird über String-Splitting ausgelesen statt sauberem JSON, 
  funktioniert, kann aber Fehler verursachen
- Läuft aktuell nur lokal (localhost)

Baue das gerade nach und nach aus, während ich n8n lerne.
