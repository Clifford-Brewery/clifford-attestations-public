# Clifford – Public Attestations
This repository is the **public index** of attestations: small, signed statements
that attach evidence to claims we make (e.g., accessibility, age policy, sourcing).

It’s intentionally simple: a JSON index plus any public, non-sensitive artifacts.

---

## What’s in here
- `index.json` – the public catalog (see schema below)
- `/evidence/` – optional public evidence (redact or link out if sensitive)
- README (this file)

**Example `index.json`**
```json
[
  {
    "id": "2025-10-07-trivia-accessible",
    "scope": "event",
    "subject": "Trivia Night – Oct 30, 2025",
    "claim": "Accessible seating available; washroom on main floor.",
    "when": "2025-10-07T16:10:00-04:00",
    "who": { "name": "Clifford Brewing Co.", "role": "Host" },
    "evidence": [
      {"type":"photo","url":"./evidence/accessible-seats.jpg"},
      {"type":"policy","url":"https://cliffordbrewing.com/accessibility"}
    ],
    "contact": "info@cliffordbrewing.com",
    "tags": ["accessibility","all-ages"],
    "signature": {
      "type": "detached-sha256",
      "digest": "abc123... (optional)"
    }
  }
]
````

**Field guide**

* `id` – stable identifier (date + short slug)
* `scope` – `event`, `promotion`, `policy`, `product`, etc.
* `subject` – human label for what this applies to
* `claim` – the public-facing statement
* `when` – ISO timestamp with timezone offset
* `who` – the attesting party (org/person)
* `evidence` – links to public artefacts (or external sources)
* `contact` – public inbox for questions
* `tags` – simple keywords for grouping/search
* `signature` – optional hash or signature reference

> Do **not** publish personal or sensitive data here. Link to public pages or
> redacted artefacts only. Keep drafts in the private repo:
> `Clifford-Brewery/clifford-attestations`.

---

## How new attestations flow

1. Draft in **private** repo (`clifford-attestations`) with any sensitive context.
2. Approver review (human in the loop).
3. Publish a **minimal** public record here (`index.json` + public evidence links).
4. Reference the attestation from the site or event page.

---

## Contributing

* Small changes: open a PR editing `index.json`.
* Bigger changes: add files under `evidence/` and reference them in the index.
* Keep PR descriptions clear (who/what/when/why).
* CI/lint **not required**; we keep the format intentionally simple.

---

## License

Unless otherwise noted, content here is © Clifford Brewing Co. and released under
**CC BY 4.0** for public reuse of the attestation entries themselves.

