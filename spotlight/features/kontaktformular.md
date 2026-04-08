---
title: Kontaktformular
order: 3
excerpt: E-Mail-Kontaktformulare ohne externe Dienste
---

# Kontaktformular

Spotlight hat einen eingebauten Mail-Endpoint, über den du Kontaktformulare ohne externe Dienste versenden kannst. Voraussetzung: [SMTP ist eingerichtet](/spotlight/guide/erste-schritte/smtp-einrichten).

## Minimales Beispiel

```html
<form action="/api/contact" method="POST">
  <label>
    Name
    <input name="name" type="text" required>
  </label>
  <label>
    E-Mail
    <input name="email" type="email" required>
  </label>
  <label>
    Nachricht
    <textarea name="message" rows="5" required></textarea>
  </label>
  <button type="submit">Senden</button>
</form>
```

Das Formular schickt die Daten als `POST` an `/api/contact`. Spotlight sendet eine E-Mail an die im SMTP-Setting hinterlegte `From`-Adresse.

## Mit JavaScript (kein Reload)

```html
<form id="contact-form">
  <input name="name" required>
  <input name="email" type="email" required>
  <textarea name="message" required></textarea>
  <button type="submit">Senden</button>
  <p id="status" hidden></p>
</form>

<script>
  const form = document.getElementById('contact-form');
  const status = document.getElementById('status');

  form.addEventListener('submit', async (e) => {
    e.preventDefault();
    const data = Object.fromEntries(new FormData(form));

    const res = await fetch('/api/contact', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(data),
    });

    status.hidden = false;
    status.textContent = res.ok ? '✓ Nachricht gesendet!' : '✗ Fehler beim Senden.';
    if (res.ok) form.reset();
  });
</script>
```

## Ziel-E-Mail konfigurieren

Standardmäßig geht die Nachricht an die `From`-Adresse in deinen SMTP-Einstellungen. Wenn du eine andere Empfänger-Adresse willst, kannst du sie im Formular als `hidden` Feld setzen:

```html
<input type="hidden" name="to" value="kontakt@meine-website.de">
```

Oder unter **Einstellungen > Kontaktformular** einmal global setzen.

## Spam-Schutz

Spotlight hat einen eingebauten **Honeypot**:

```html
<input type="text" name="website" tabindex="-1" autocomplete="off" style="display:none">
```

Füge das versteckte Feld `website` hinzu — wenn es befüllt ist, geht die Nachricht nicht raus (Bot erkannt).

Für höheren Schutz kannst du zusätzlich **Cloudflare Turnstile** oder **hCaptcha** integrieren — die Challenge wird serverseitig validiert.

## Dateianhänge

Mit `multipart/form-data` kannst du auch Dateien anhängen:

```html
<form action="/api/contact" method="POST" enctype="multipart/form-data">
  <input name="email" type="email" required>
  <textarea name="message" required></textarea>
  <input name="attachment" type="file" accept=".pdf,.jpg,.png">
  <button type="submit">Senden</button>
</form>
```

Max. Dateigröße: 10 MB pro Anhang.
