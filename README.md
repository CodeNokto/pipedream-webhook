# Pipedream Webhook-endepunkt

API-endepunkt som mottar og logger en JSON-payload fra eksterne systemer.

## Bruksområde

- Integrasjon mellom applikasjoner
- Logging av innkommende data

## Funksjon

- Validerer at payload faktisk er mottatt
- Logger payload som "received_payload"
- Returnerer statusmelding ("ok" eller "error")

## Eksempel på respons

```json
{
  "status": "ok",
  "message": "Payload mottatt",
  "payload": { /* innhold */ }
}
