# Physical and Environmental Security Policy

| Field | Value |
|---|---|
| Document ID | NH-POL-005 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 5 February 2027 |
| Owner | Rania Fouad, Office Manager |
| Approved by | Dina Mostafa, COO |
| Classification | Internal (simulated client confidential) |
| Next review | February 2028 |

> **Simulation notice:** Nabd Health is fictional. This policy is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This policy protects the Cairo office (L-01), its people, equipment, and network
facilities from unauthorized access, damage, and environmental threats. It implements
Annex A controls A.7.1 to A.7.14.

## 2. Scope

Applies to the Nabd office, the network cupboard, reception, support floor, storage
areas, and all equipment located there. Remote working locations are covered by
NH-POL-013.

## 3. Physical perimeter and entry

1. The office is on the second floor of a multi-tenant building with a landlord security
   desk in the lobby.
2. Office entry uses the fob system. Fobs are issued only to staff and contractors who
   require regular access.
3. The Office Manager reconciles fobs against the staff list quarterly and disables lost
   or unreturned fobs immediately.
4. Visitors sign in at reception, are escorted at all times, and are recorded in the
   visitor log. Unescorted visitors are challenged by any staff member.
5. Delivery personnel remain in reception. Deliveries are not left in the open-plan
   area.
6. Access outside normal hours requires Office Manager approval and is logged.

## 4. Securing offices and facilities

- The network cupboard is locked, with keys held by the Office Manager and IT Support
  Officer. Access is logged.
- Spare laptops and equipment are stored in a locked cabinet.
- Support areas are separated from general meeting space where practical.
- Doors and windows are secured at the end of the day; the last person out checks the
  office.
- Keys and fobs are not shared or copied.

## 5. Physical monitoring

CCTV covers reception and the main entrance, with 14-day retention. Footage is accessed
only by the Office Manager for security or investigation purposes and is logged.
Monitoring is proportionate and does not cover private areas. Coverage of the network
cupboard is scheduled for review in Q3 2027.

## 6. Environmental protection

| Threat | Control |
|---|---|
| Fire | Building alarm, extinguishers, evacuation plan, fire drills |
| Power loss | UPS for the network cupboard (about 20 minutes); critical services are cloud-hosted |
| Water or building damage | Equipment raised and away from windows; landlord escalation |
| Temperature | Office air conditioning; equipment in ventilated cupboard |
| Connectivity loss | Secondary ISP connection; failover tested quarterly |

## 7. Clear desk and clear screen

- Lock screens when leaving a device.
- Remove patient documents and removable media from desks at the end of the day.
- Use secure print release and collect output immediately.
- Erase whiteboards containing patient or incident information.
- The Office Manager performs quarterly spot checks and records results.

## 8. Equipment siting and maintenance

Equipment is sited away from walkways, water sources, and public areas. Maintenance is
performed by approved providers, and devices with security faults are removed from
service until repaired. Asset records are updated after repair or replacement.

## 9. Off-premises equipment

Staff and contractors take laptops and phones off-site daily. Devices must be managed,
encrypted, and protected in transit. Loss or theft must be reported immediately so that
remote wipe and access revocation can be performed.

## 10. Storage media

Removable media use is exceptional and requires CTO approval. Approved media must be
encrypted and recorded in the media register. Media containing Highly Confidential
information must be wiped or destroyed before disposal.

## 11. Disposal and reuse

1. Devices leaving Nabd are wiped using a certified method or physically destroyed.
2. A disposal register records asset ID, serial number, date, method, and certificate.
3. Devices are not sold or given to staff without a wipe certificate.
4. Paper containing confidential information is cross-cut shredded.

## 12. Roles

| Role | Responsibility |
|---|---|
| Office Manager | Fobs, visitors, keys, CCTV, clear desk checks, landlord liaison |
| IT Support Officer | Equipment, maintenance, disposal, device inventory |
| COO | Approves physical security changes and exceptions |
| All staff | Follow entry, visitor, clear desk, and equipment rules |

## 13. Related documents

- NH-POL-003 Acceptable Use and Information Handling Policy
- NH-POL-013 Remote Working and Mobile Device Policy
- NH-REG-001 Asset Register
- NH-PRC-003 Incident Response Plan

## 14. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 5 February 2027 | Initial physical and environmental security policy | Office Manager |
