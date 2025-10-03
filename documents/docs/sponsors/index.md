---
title: Sponsorship Support
description: Thanks to all sponsors for their support
sidebar: false
outline: deep
---

<script setup>
import SponsorsList from './SponsorsList.vue'
</script>

<div class="sponsors-page">

# Sponsorship Support

<div class="header-content">
  <h2>Thanks to all sponsors for their support ❤️</h2>
</div>

<div class="sponsors-section">


<SponsorsList />

## Become a Sponsor

Please support through the following methods:
Your sponsorship will be used for:
- Supporting device compatibility testing
- New feature development and maintenance


<div class="payment-container">
  <div class="payment-method">
    <h4>WeChat Pay</h4>
    <div class="qr-code">
      <img src="./images/zsm.jpg" alt="WeChat Payment QR Code">
    </div>
  </div>
</div>

### Device Compatibility Support

You can support device compatibility through the following ways:
- Specify your device model in the sponsorship notes, I will prioritize support for these devices
- Directly sponsor/donate hardware devices to help with development and compatibility testing
- Provide detailed device parameters and usage scenarios to facilitate better development

::: tip Contact Information
For hardware sponsorship, please contact me via the email on the GitHub homepage to discuss shipping methods and addresses
:::

</div>

</div>

<style>
.sponsors-page {
  max-width: 900px;
  margin: 0 auto;
  padding: 2rem 1.5rem;
}

.sponsors-page h1 {
  text-align: center;
  margin-bottom: 1rem;
}

.header-content {
  text-align: center;
}

.header-content h2 {
  color: var(--vp-c-brand);
  margin-bottom: 1rem;
}

.sponsors-section h2, .sponsors-section h3 {
  margin-top: 3rem;
  padding-top: 1rem;
  border-top: 1px solid var(--vp-c-divider);
}

.payment-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 2.5rem;
  margin: 2rem 0;
}

.payment-method {
  text-align: center;
  border: 1px solid var(--vp-c-divider);
  border-radius: 8px;
  padding: 1.5rem;
  transition: all 0.3s ease;
}

.payment-method:hover {
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  transform: translateY(-5px);
}

.payment-method h4 {
  margin-top: 0;
  margin-bottom: 1rem;
}

.qr-code {
  width: 200px;
  height: 200px;
  margin: 0 auto;
  overflow: hidden;
}

.qr-code img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

@media (max-width: 768px) {
  .payment-container {
    grid-template-columns: 1fr;
  }
  
  .qr-code {
    width: 180px;
    height: 180px;
  }
}
</style>
