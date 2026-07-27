# Nurelo — Aktivierungsseite

Statische Weiterleitungsseite für Lizenz-Aktivierungslinks. Nimmt einen Token
aus der Adresszeile entgegen und leitet auf `nurelo://activate?token=…` weiter,
sodass sich die Nurelo-Desktop-App öffnet und die Lizenz selbst aktiviert.

    https://iketone.github.io/nurelo-activation-page/?token=<token>

Die Seite prüft den Token **nicht** — das passiert erst in der Supabase-Function
`validate`, wenn die App sich meldet. Hier wird nur das Format geprüft, bevor
der Wert in einen Link geschrieben wird.

## Warum ein eigenes Repo?

Supabase Edge Functions können auf `*.supabase.co` kein HTML ausliefern: Die
Plattform erzwingt aus Phishing-Schutz `Content-Type: text/plain` und eine
restriktive `Content-Security-Policy`, die sowohl Skripte als auch die
Weiterleitung auf ein eigenes URL-Schema blockiert.

## Quelle

Die gepflegte Fassung liegt im Adminzentrale-Projekt unter `web/index.html`
(Repo `nurelo-admin`). Änderungen bitte dort vornehmen und anschließend
hierher kopieren — nicht direkt hier bearbeiten.

Die Adresse dieser Seite wird in der Adminzentrale unter
*Konfiguration → `aktivierung_url`* hinterlegt.
