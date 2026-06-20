---
layout: page
title: Deep Steganography
description: Neural networks that hide an image within another image, with a second model that extracts the hidden content.
img:
importance: 2
category: AI/ML
---

This project explores deep learning-based steganography: hiding information inside other information. Neural networks embed a secret image inside a cover image in a way that remains difficult to detect visually.

## Overview

The system uses one model to encode a secret image into a cover image, then another model to recover the hidden image from the encoded result.

## How It Works

1. **Encoding Network** - Takes a cover image and a secret image, then produces an encoded image that visually resembles the cover image.
2. **Decoding Network** - Extracts the hidden image from the encoded image.

## Applications

- Encrypted message transmission
- Digital watermarking
- Secure communication channels
- Copyright protection
