Ecosocial AI Automation

AI-powered social media automation for Ecosphere using n8n, Ollama, Cloudflare AI/Browser Rendering, webhooks, and the Meta Graph API.

What this project does

Reads product pages from the Ecosphere stationery website.

Selects one product for the day.

Extracts the product name, description, image, and URL.

Uses Ollama to generate social-media content.

Uses the real product image as reference for AI-assisted visual generation.

Builds a 4-slide Instagram carousel and a Facebook creative using HTML/CSS.

Renders the creatives to JPEG files.

Saves the generated images on the n8n server.

Serves images through a public webhook so Meta can fetch them.

Creates and publishes an Instagram carousel.

Publishes a Facebook image post.

Technologies

n8n

Ollama / Qwen

JavaScript

HTML/CSS

Cloudflare AI

Cloudflare Browser Rendering

Meta Graph API

Webhooks

VPS / Docker

High-level flow

Schedule Trigger
  -> Get Ecosphere Products
  -> Extract Product Links
  -> Select Today's Product
  -> Get Product Page
  -> Extract Product Data
  -> Ollama Generate Social Content
  -> Parse Social Content
  -> Download Product Image
  -> Prepare AI Image Prompt
  -> Generate AI Product Visual
  -> Build HTML/CSS Creatives
  -> Render Instagram Slides + Facebook Post
  -> Save Images
  -> Public Image Webhook
  -> Instagram Carousel + Facebook Publishing

Security

This repository contains a sanitized public workflow template.

Real production values have been removed, including:

Meta access tokens

Cloudflare API tokens

n8n credential references

private infrastructure values

Use n8n Credentials or secure environment variables for secrets. Never commit real production secrets to GitHub.

Placeholders to configure

Replace these in your private setup:

YOUR_OLLAMA_HOST

YOUR_CLOUDFLARE_ACCOUNT_ID

YOUR_CLOUDFLARE_API_TOKEN

YOUR_META_ACCESS_TOKEN

YOUR_INSTAGRAM_BUSINESS_ID

YOUR_FACEBOOK_PAGE_ID

YOUR_N8N_DOMAIN

Current status

The workflow architecture, AI content generation, creative rendering, local file handling, and public image-serving webhook are implemented.

Instagram carousel and Facebook publishing are being tested and hardened with retry/error handling.

LinkedIn integration was explored separately and is not included in the public working flow.

Key engineering lessons

External social APIs need publicly reachable media URLs.

Binary images must be returned with the correct MIME type.

Small field-name mismatches can break a workflow.

Media APIs may require status checks and waits before publishing.

Long AI/image-generation calls need timeout and retry handling.

Suggested repository structure

workflow/
  ecosphere-social-media-automation-safe.json

docs/
  automation-documentation.pdf
  automation-documentation.docx

screenshots/
  workflow-overview.png

README.md
.env.example
LICENSE# Ecosocial-AI-automation
AI-powered social media automation using n8n, Ollama, Meta Graph API, webhooks, and automated Instagram/Facebook publishing.
