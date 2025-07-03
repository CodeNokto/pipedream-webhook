// Webhook-endepunkt: Tar imot og logger payload, svarer med status.
// Bruk: Integrasjon med eksterne systemer (Pipedream).

export default defineComponent({
  async run({ steps, $ }) {
    try {
      const payload = steps.trigger.event.body;
      if (!payload) {
        throw new Error("Ingen payload mottatt");
      }
      $.export("received_payload", payload);
      return {
        status: "ok",
        message: "Payload mottatt",
        payload
      };
    } catch (error) {
      $.export("error", error.message);
      return {
        status: "error",
        message: error.message
      };
    }
  }
});
