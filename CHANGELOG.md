# Changelog

## 1.0.1

- no change to what it offers

Each public type checked against Anthropic's API reference for the
Messages API and its streamed events: every field's name, whether it is
optional, and its type match what Anthropic sends and accepts. A stream's
`error` event is now named among its event types. Message content and the
system prompt are now marked as deliberately not counted as personal data
here, because Jadpo checks what an app sends a model where the app writes
it. Nothing an app writes changes.

## 1.0.0

- first release

Fills the `ai` capability through Anthropic's Messages API: `ai.generate`
with its structured outputs (`output_config.format`), and `ai.stream` as
its streamed events. Anthropic has no embeddings endpoint, so `ai.embed`
isn't mapped. Each model's context window and price are as Anthropic's
pages gave them on 2026-10-20.
