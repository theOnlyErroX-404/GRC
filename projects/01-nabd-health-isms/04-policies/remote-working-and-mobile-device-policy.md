# Remote Working and Mobile Device Policy

| Field | Value |
|---|---|
| Document ID | NH-POL-013 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 26 February 2027 |
| Owner | Dina Mostafa, COO |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |
| Next review | February 2028 |

> **Simulation notice:** Nabd Health is fictional. This policy is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This policy defines security requirements for remote working, mobile devices, and
off-site use of Nabd information. It implements Annex A controls A.6.7, A.7.9, A.8.1,
A.8.7, A.8.23, and supports A.5.10.

## 2. Scope

Applies to all staff and contractors who work outside the Cairo office or use laptops,
phones, tablets, or personal devices for Nabd work. About 40 percent of staff work
remotely on a typical day.

## 3. Approval and suitability

1. Remote working is approved by the line manager and recorded in HR records.
2. The employee must have a private space where patient data cannot be seen or overheard.
3. Home networks must use WPA2 or WPA3 and a strong password; public Wi-Fi requires the
   company VPN.
4. Remote access to production requires a managed device, VPN, and MFA.
5. Staff who cannot meet the requirements must work from the office or use an approved
   alternative.

## 4. Devices

### 4.1 Company-managed devices

- Encrypted with FileVault or BitLocker and enrolled in MDM.
- Screen lock after five minutes, enforced by policy.
- Endpoint protection enabled and updated.
- OS and application patches installed within the defined SLA.
- No local administrator rights without IT approval.
- Remote wipe enabled and tested.

### 4.2 Personal devices

- May access email, Slack, and calendar only through the approved MDM profile.
- Patient data must not be stored on personal devices.
- Screen lock and encryption are required; jailbroken or rooted devices are prohibited.
- Nabd may remove company data remotely without affecting personal data.
- Camera and microphone access to patient systems is limited to approved apps.

### 4.3 Contractor devices

Pixelwave contractors must meet the same minimum requirements: supported OS, disk
encryption, screen lock, endpoint protection, and prompt patching. They access only the
mobile repositories and staging environment, not production. Compliance is confirmed at
onboarding and annually.

## 5. Working outside the office

- Lock the screen when leaving the device, even briefly.
- Do not leave devices or documents visible in cars, cafes, or shared spaces.
- Use a privacy screen in public spaces when viewing confidential information.
- Do not print patient documents outside the office.
- Do not use public computers or shared printers for Nabd work.
- Report theft or loss immediately so that access can be revoked and the device wiped.

## 6. Network and access

1. Use the company VPN for production and Admin Panel access.
2. Do not disable the VPN, firewall, or endpoint protection.
3. Do not use split tunneling for production traffic.
4. Guest and home networks must not expose file sharing or remote desktop services.
5. Web filtering applies on the office network and through browser protections on
   managed devices.

## 7. Mobile phones

- Company email and Slack require a screen lock and the MDM profile.
- OTP and MFA apps must not be shared or backed up to personal accounts.
- Lost phones must be reported immediately; the MDM profile is wiped remotely.
- Patient data must not be photographed or stored in personal photo libraries.

## 8. Clear desk and clear screen at home

The clear desk and clear screen rules in NH-POL-003 apply at home. Patient documents must
not be left in shared living areas, and screens must be locked when not in use.

## 9. Return and termination

Devices, chargers, and accessories are returned at the end of employment or engagement.
The MDM profile is removed only after data is wiped. Personal devices are removed from
the MDM profile after confirmation that company data is deleted.

## 10. Roles

| Role | Responsibility |
|---|---|
| COO | Owns the remote working arrangement and approves exceptions |
| IT Support Officer | Manages MDM, device compliance, and wipes |
| Line managers | Confirm suitability and monitor compliance |
| CTO | Approves technical remote access methods |
| Staff and contractors | Follow this policy and report loss or compromise |

## 11. Related documents

- NH-POL-002 Access Control Policy
- NH-POL-003 Acceptable Use and Information Handling Policy
- NH-POL-005 Physical and Environmental Security Policy
- NH-POL-010 Vulnerability and Configuration Management Policy
- NH-PRC-001 Onboarding and Offboarding Procedure

## 12. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 26 February 2027 | Initial remote working and mobile device policy | COO |
