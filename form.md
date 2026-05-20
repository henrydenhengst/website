---
title: Contact
form:
    name: contactformulier
    template: formdata
    action: /contact
    
    fields:
        - name: naam
          label: Hoe heet je?
          placeholder: Je volledige naam
          type: text
          validate:
            required: true

        - name: email
          label: E-mailadres
          placeholder: Je e-mailadres voor antwoord
          type: email
          validate:
            required: true

        - name: onderwerp
          label: Onderwerp
          type: select
          options:
            vraag: Ik heb een algemene vraag
            reparatie: Ik wil IT-apparatuur laten repareren
            donatie: Ik wil IT-apparatuur doneren
            aanvraag: Ik wil een computer aanvragen
            vrijwilliger: Ik wil vrijwilliger worden
            anders: Andere vraag

        - name: bericht
          label: Je bericht
          placeholder: Waarmee kunnen we je helpen?
          type: textarea
          validate:
            required: true

    buttons:
        - type: submit
          value: Bericht versturen
        - type: reset
          value: Wissen

    process:
        - email:
            from: "{{ config.plugins.email.from }}"
            to: "vcp5693@duck.com"
            reply_to: "{{ form.value.email }}"
            subject: "[Stichting LKCC] Contact van {{ form.value.naam|e }}"
            body: "{% include 'forms/data.html.twig' %}"
        - message: "Bedankt voor je bericht! We nemen zo snel mogelijk contact met je op."
        - display: /bedankt
---

# Contact

Heb je een vraag, wil je apparatuur doneren of heb je hulp nodig? Neem dan contact met ons op via onderstaand formulier.

We proberen je bericht binnen **2 werkdagen** te beantwoorden.

---

[Cookie Beleid (EU)](https://st-lkcc.nl/cookiebeleid-eu/)

> © 2026 **Stichting Linux Kennis Computer Centrum** | KvK: 82063214 | SBI 94993 | RSIN: 862322431 | [ANBI-status](https://st-lkcc.nl/blog/2025/05/17/bestuurlijke-stukken-stichting-linux-kennis-computer-centrum/)