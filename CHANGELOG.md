# Changelog

## 2.0.0

- retyped type `MessageRequest`
- retyped type `StreamedMessageRequest`

Each public type checked against Anthropic's API reference for the
Messages API and its streamed events: every field's name, whether it is
optional, and its type match what Anthropic sends and accepts. A stream's
`error` event is now named among its event types. Message content and the
system prompt are marked as deliberately not counted as personal data
here, because Jadpo checks what an app sends a model where the app writes
it.

A request, streamed or not, now takes at most 100,000 messages, the limit
Anthropic's API reference gives for one request, so one Anthropic would
refuse is refused before it is sent. Narrowing what a request takes is a
breaking change, so the package is `Anthropic.v2`: an app moves to it by
changing its package.

## 1.0.0

- first release

Fills the `ai` capability through Anthropic's Messages API: `ai.generate`
with its structured outputs (`output_config.format`), and `ai.stream` as
its streamed events. Anthropic has no embeddings endpoint, so `ai.embed`
isn't mapped. Each model's context window and price are as Anthropic's
pages gave them on 2026-10-20.
