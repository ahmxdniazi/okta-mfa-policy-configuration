# Okta MFA Configuration — Technical Reference

## Authentication Policy Rule Details

### Rule 1: Require MFA for All Users (Priority 1)

**Conditions (IF):**

| Parameter | Value |
|-----------|-------|
| User's user type | Any user type |
| User's group membership includes | Any group |
| User is | Any user |
| Device state is | Any |
| Device assurance policy is | No policy |
| Device platform is | Any platform |
| User's IP is | Any IP |
| Risk is | Any |

**Actions (THEN):**

| Parameter | Value |
|-----------|-------|
| Access | Allowed |
| Authentication requirement | Password + another factor |
| Password factor | Password (Knowledge) |
| Additional factor | Okta Verify – TOTP **or** Okta Verify – FastPass |
| Authentication methods | Allow any method that can meet the requirement |
| Password re-auth frequency | Every 1 hour |
| Other authenticator re-auth frequency | Every 1 hour |

---

### Rule 2: Catch-all Rule (Priority 2)

| Parameter | Value |
|-----------|-------|
| Trigger | Any request (fallback) |
| Access | Allowed with any 2 factor types |
| Factor types | Knowledge / Biometric |
| Options | Password **or** Okta Verify – FastPass |

---

## Authenticator Configuration

| Authenticator | Factor Type | Characteristics | Status |
|--------------|-------------|-----------------|--------|
| Email | Possession | — | Active |
| Okta Verify | Possession / Possession+Knowledge / Possession+Biometric | Device bound, Hardware protected, Phishing resistant (FastPass) | Active |
| Password | Knowledge | — | Active |

---

## Application Assignment

- **Application:** Okta Dashboard
- **Authentication Policy:** Require MFA Policy
- **Integration Protocol:** SAML 2.0
- **Org:** isb-nu-integrator-7188680

---

## Okta Org Details

| Field | Value |
|-------|-------|
| Org ID | isb-nu-integrator-7188680 |
| Plan | Integrator Free Plan |
| Active Users | 6 of 10 |
| Test User | sarmadfarooq@cyber.com |
