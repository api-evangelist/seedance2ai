---
name: post-video
description: Generate a high-quality cinematic video using Seedance2AI's text-to-video generation endpoint, demonstrating full request construction and polling for task completion
api: https://www.seedance2ai.io/api/v1/video/{videoid}
operations:
  - post_api_v1_video_videoid
---

## Steps
1. **Prepare request body** with `mode`, `quality_tier`, `prompt`, `aspect_ratio`, `duration`, `resolution` as documented.
2. **POST** to the endpoint using your API key in the `Authorization: Bearer $SEEDANCE_API_KEY` header.
3. **Handle response** – on `201` you receive video metadata including `id` and `status`.
4. **Poll task status** using `GET /api/v1/tasks/{id}` until `status` is `completed`.

## Idempotency
Include an `Idempotency-Key` header for safe retries.
