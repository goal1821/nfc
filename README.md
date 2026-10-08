# Petvewi NFC identity card demo

Public static demo with fictional contact information. No database or local server is required.

- Cat: c.html (NFCCAT000001)
- Dog: d.html (NFCDEMO00001)
- Other: o.html (NFCOTHER0001)
- Query entry: ?id=NFCCAT000001

Enable GitHub Pages from the main branch root. Write the HTTPS page URL as the first NFC NDEF URI record. iPhone shows a notification; tap it to open the webpage.

This demo does not sync database changes or record scans. The App button requires a separately configured installed app and reachable backend.
