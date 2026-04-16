# 🚀 Klasse 2b - Smart Checklist

Eine moderne, sichere Web-App zur Statusverfolgung von Aufgaben oder Abgaben in der Schule. Diese App kombiniert **Einfachheit für Nutzer** mit **echter Sicherheit für Admins**.

## 🌟 Features
* **Live-Status:** Schüler oder Eltern können den Bearbeitungsstatus ("🎨 Arbeit", "✅ Fertig") in Echtzeit einsehen und ändern.
* **Fortschrittsbalken:** Visualisiert sofort den aktuellen Stand der gesamten Klasse.
* **Admin-Kontrolle:** Sensible Checkboxen (z.B. "Unterlagen erhalten") sind geschützt und können nur von autorisierten Personen bedient werden.
* **Dark Mode Design:** Optimiert für mobile Endgeräte und Desktop mit modernem Tailwind CSS.

## 🛡️ Sicherheit & Technologie
Die App nutzt ein **hybrides Sicherheitskonzept**:

* **Frontend:** Entwickelt mit HTML5 und Tailwind CSS.
* **Backend:** Powered by [Supabase](https://supabase.com/) (PostgreSQL).
* **Authentifizierung:** Sicherer **Google OAuth 2.0 Login** – kein Passwort-Management nötig.
* **Datenbank-Schutz:** Echte Sicherheit durch **Row Level Security (RLS)** direkt in der Datenbank. Selbst wenn das UI manipuliert wird, lehnt die Datenbank unbefugte Änderungen ab.

## 🛠️ Setup & Admin-Verwaltung

### 1. Einen neuen Admin hinzufügen
Wenn ein Kollege oder eine Hilfskraft ebenfalls Checkboxen bedienen soll, muss deren E-Mail in der Supabase SQL-Konsole freigeschaltet werden:

```sql
-- Beispiel: Einen zweiten Admin hinzufügen
ALTER POLICY "3_update_checkbox_admin" ON schueler_status 
USING (auth.email() = 'rusmiromer@gmail.com' OR auth.email() = 'kollege@gmail.com');
```

### 2. Vielseitige Nutzungsmöglichkeiten

Diese App ist nicht nur für die Schule! Sie lässt sich leicht anpassen für:

Vereine: Wer hat seinen Mitgliedsbeitrag gezahlt?

Events: Wer hat die Einladung bestätigt?

Projekte: Welche Teilaufgaben sind bereits physisch geprüft?
