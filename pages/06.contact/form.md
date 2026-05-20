---
title: Contact
form:
    name: contact-form
    action: /contact/bedankt
    method: POST
    fields:
        - name: name
          label: Naam
          placeholder: Uw volledige naam
          autocomplete: on
          type: text
          validate:
            required: true
        - name: email
          label: E-mailadres
          placeholder: Uw e-mailadres
          type: email
          validate:
            required: true
        - name: message
          label: Bericht
          placeholder: Typ hier uw bericht...
          type: textarea
          rows: 5
          validate:
            required: true
    buttons:
        - type: submit
          value: Verzenden
        - type: reset
          value: Wissen
    process:
        - email:
            from: "{{ config.plugins.email.from }}"
            to: "linuxkcc@gmail.com"
            subject: "[Contactformulier Website] {{ form.value.name|e }}"
            body: "{% include 'forms/data.html.twig' %}"
        - redirect: /contact/bedankt
process:
    twig: true
---

# Contact met Stichting Linux Kennis Computer Centrum

Heeft u vragen over onze projecten, wilt u samenwerken of overweegt u een donatie? Wij staan u graag te woord.

***

## Direct Contact
* **E-mail:** linuxkcc@gmail.com
* **Telefoon:** 0181-750 714 / 06-28.92.72.99
* **Persvoorlichting:** linuxkcc@gmail.com

### Bezoek- en Postadres
Stichting Linux Kennis Computer Centrum  
Zalm 7,  
3225 XM Hellevoetsluis.  

***

## Formele Gegevens (Colofon)
Voor officiële correspondentie en verificatie vindt u hieronder onze juridische gegevens:

* **Statutaire Naam:** Stichting Linux Kennis Computer Centrum
* **KvK-nummer:** 82063214 (Ingeschreven bij de Kamer van Koophandel)
* **RSIN:** 862322431
* **SBI-code:** 94993

***

## Stuur ons een bericht

{% include "forms/form.html.twig" with { form: page.form } %}

***

## Privacy & Gegevens
Stichting Linux Kennis Computer Centrum gaat zorgvuldig om met uw persoonsgegevens. Wanneer u contact met ons opneemt, worden uw gegevens uitsluitend gebruikt om uw vraag te beantwoorden. 

* Zie onze [Privacyverklaring](../privacy) voor meer informatie over hoe wij uw data protecten.

> © 2026 **Stichting Linux Kennis Computer Centrum** | KvK: 82063214 | SBI 94993 | RSIN: 862322431 | [ANBI-status](https://st-lkcc.nl/blog/2025/05/17/bestuurlijke-stukken-stichting-linux-kennis-computer-centrum/)
