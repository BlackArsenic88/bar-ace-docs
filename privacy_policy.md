# Privacy Policy

**Last Updated: September 23, 2026**

Bar Ace Inc. ("Company," "we," "us," or "our") is committed to protecting your privacy. This Privacy Policy explains how we collect, use, disclose, and safeguard your personal information when you use our mobile application and related services (collectively, the "Service").

---

## 1. Information We Collect

We collect information directly from you, automatically through your device, and via sync transactions.

### 1.1 Personal Data You Provide
* **Account Credentials:** Email address, full name, and password created during registration.
* **User Study Data:** Written essay drafts, MPT submissions, custom flashcards, study bookmarks, and flagged questions.
* **Payment Data:** Subscription and purchase records. *Note: Full credit card and financial details are processed securely by Apple App Store or Google Play Store and are never stored on our servers.*

### 1.2 Automatically Collected Technical Data
* **Device & Usage Identifiers:** Device model, operating system version (iOS/Android), unique device identifiers, IP address, and network state.
* **Performance & Diagnostics:** App launch times, crash logs, frame rates, API response times, and memory metrics.
* **Study Analytics:** Question accuracy rates, completion times per question type, subject strengths, and spaced-repetition performance metrics.

---

## 2. How We Use Your Information

We process your data for the following core purposes:
1. **To Provide the Service:** Operating test engines, rendering study analytics, calculating Spaced Repetition System (SRS) intervals, and saving essay drafts.
2. **Cross-Device Synchronization:** Syncing your test progress, bookmarks, and flashcards across devices using delta-based cloud updates.
3. **Application Optimization:** Analyzing aggregate performance data to lower load times below 2 seconds and eliminate frame drops during text editing.
4. **Customer Support:** Resolving technical inquiries and verifying account standing.
5. **Security & Integrity:** Preventing content scraping, unauthorized account access, and unauthorized distribution of proprietary UBE content.

---

## 3. Local Storage & Offline-First Architecture

Bar Ace utilizes an **Offline-First Data Model**:
* Practice history, flashcards, and essay drafts are stored locally on your device using encrypted key-value caches (`MMKV`) and local database structures (`SQLite` / `WatermelonDB`).
* When an active internet connection is detected, local mutation queues sync with our secure server using encrypted HTTPS/TLS channels.

---

## 4. How We Share Your Information

We **do not sell, rent, or trade** your personal data to third parties or advertisers. We share information only in the following limited circumstances:

* **Service Providers:** Cloud infrastructure providers (e.g., AWS, GCP), app analytics platforms, and error tracking tools (e.g., Sentry) that assist in operating our app under strict confidentiality obligations.
* **App Store Platforms:** Apple and Google for processing transactions and managing subscription statuses.
* **Legal Requirements:** If required by law, subpoena, or government order to protect our legal rights or user safety.

---

## 5. Data Security

We implement industry-standard physical, administrative, and technical safeguards designed to protect your data against unauthorized access, loss, or alteration. These measures include:
* Full transport encryption via TLS 1.3 for all data in transit.
* Encryption of local device caches where applicable.
* Strict API security controls using Google Play Integrity and Apple App Attest to prevent unauthorized access.

However, no method of transmission over the internet or electronic storage is 100% secure. You are responsible for protecting your account credentials.

---

## 6. Data Retention and Deletion

We retain your personal data for as long as your account remains active or as needed to provide you with the Service. 

### Account Deletion
You can request account deletion at any time within the application settings or by contacting `privacy@barace.app`. Upon account deletion:
* Your account records, study history, and flashcards will be permanently purged from our active databases within 30 days.
* Anonymized, aggregated performance statistics (which cannot identify you) may be retained for system calibration and research.

---

## 7. Your Privacy Rights (GDPR & CCPA/CPRA Compliance)

Depending on your location, you may have the following rights regarding your personal information:
* **Right to Access:** Request a copy of the personal data we hold about you.
* **Right to Rectification:** Request correction of inaccurate or incomplete data.
* **Right to Erasure:** Request the deletion of your personal information.
* **Right to Data Portability:** Receive your user-generated study data in a structured, standard format (e.g., JSON).

To exercise any of these rights, please email us at `privacy@barace.app`.

---

## 8. Children's Privacy

The Service is intended solely for adults preparing for professional legal examinations. We do not knowingly collect personal information from individuals under 18 years of age.

---

## 9. Changes to This Privacy Policy

We may update this Privacy Policy periodically. We will notify you of material changes by updating the "Last Updated" date at the top of this document or by sending an in-app notification.

---

## 10. Contact Us

If you have questions or concerns about this Privacy Policy, please reach out to us at:

**Bar Ace Inc.**  
Privacy & Security Operations  
Email: `privacy@barace.app`  
Website: `https://barace.app`