\# Risk Register



\## Risk Assessment Method



Risks are evaluated using two primary factors:



\- \*\*Likelihood\*\* — how likely the threat is to occur

\- \*\*Impact\*\* — the potential consequence if the threat occurs



\### Risk Rating



| Likelihood | Impact | Risk Level |

|---|---|---|

| Low | Low | Low |

| Low | Medium | Low |

| Low | High | Medium |

| Medium | Low | Low |

| Medium | Medium | Medium |

| Medium | High | High |

| High | Low | Medium |

| High | Medium | High |

| High | High | Critical |



\---



\## Risk Register



| ID | Threat | STRIDE | Likelihood | Impact | Risk | Mitigation |

|---|---|---|---|---|---|---|

| R-001 | Account or session impersonation | Spoofing | Medium | High | High | Secure password hashing, session protection, HTTPOnly/SameSite cookies, MFA where applicable |

| R-002 | Unauthorized modification of application data | Tampering | Medium | High | High | Server-side validation, authorization checks, parameterized queries |

| R-003 | Insufficient audit evidence for security events | Repudiation | Medium | Medium | Medium | Security event logging, timestamps, protected audit records |

| R-004 | Exposure of sensitive application or user information | Information Disclosure | Medium | High | High | HTTPS, access controls, secure secret management, controlled error messages |

| R-005 | Excessive requests causing resource exhaustion | Denial of Service | Medium | Medium | Medium | Rate limiting, request limits, timeouts, resource monitoring |

| R-006 | Unauthorized access to privileged functionality | Elevation of Privilege | Medium | High | High | Role-based access control, least privilege, server-side authorization |



\---



\## Detailed Risk Analysis



\### R-001 — Account or Session Impersonation



\*\*Threat:\*\* An attacker may obtain or manipulate authentication or session information to impersonate a legitimate user.



\*\*Likelihood:\*\* Medium



\*\*Impact:\*\* High



\*\*Risk Level:\*\* High



\*\*Potential Consequences:\*\*

\- Unauthorized account access

\- Access to protected resources

\- Unauthorized actions performed as the victim



\*\*Recommended Controls:\*\*

\- Strong password hashing

\- Secure session configuration

\- HTTPOnly cookies

\- SameSite cookie protection

\- Multi-factor authentication where appropriate

\- Login rate limiting



\---



\### R-002 — Unauthorized Data Modification



\*\*Threat:\*\* An attacker may modify application requests or manipulate data without authorization.



\*\*Likelihood:\*\* Medium



\*\*Impact:\*\* High



\*\*Risk Level:\*\* High



\*\*Potential Consequences:\*\*

\- Loss of data integrity

\- Unauthorized account changes

\- Manipulation of application records



\*\*Recommended Controls:\*\*

\- Server-side input validation

\- Authorization checks

\- Parameterized database queries

\- Access control enforcement

\- Integrity validation



\---



\### R-003 — Insufficient Audit Evidence



\*\*Threat:\*\* Security-relevant actions may not be adequately recorded, making it difficult to determine who performed an action.



\*\*Likelihood:\*\* Medium



\*\*Impact:\*\* Medium



\*\*Risk Level:\*\* Medium



\*\*Potential Consequences:\*\*

\- Difficult incident investigation

\- Reduced accountability

\- Incomplete forensic information



\*\*Recommended Controls:\*\*

\- Authentication event logging

\- Timestamped security events

\- Protected log storage

\- Centralized monitoring where appropriate



\---



\### R-004 — Information Disclosure



\*\*Threat:\*\* Sensitive information may become accessible to unauthorized users.



\*\*Likelihood:\*\* Medium



\*\*Impact:\*\* High



\*\*Risk Level:\*\* High



\*\*Potential Consequences:\*\*

\- Exposure of user information

\- Credential compromise

\- Privacy impact

\- Additional attacks using disclosed information



\*\*Recommended Controls:\*\*

\- HTTPS

\- Appropriate access controls

\- Secure session management

\- Secure secret management

\- Avoid sensitive information in error messages

\- Encryption where appropriate



\---



\### R-005 — Resource Exhaustion



\*\*Threat:\*\* Excessive or specially crafted requests may consume application resources.



\*\*Likelihood:\*\* Medium



\*\*Impact:\*\* Medium



\*\*Risk Level:\*\* Medium



\*\*Potential Consequences:\*\*

\- Increased response times

\- Resource exhaustion

\- Temporary service unavailability



\*\*Recommended Controls:\*\*

\- Rate limiting

\- Request size limits

\- Timeouts

\- Resource monitoring

\- Infrastructure-level protections where appropriate



\---



\### R-006 — Privilege Escalation



\*\*Threat:\*\* A lower-privileged user may attempt to access functionality intended for administrators or other authorized roles.



\*\*Likelihood:\*\* Medium



\*\*Impact:\*\* High



\*\*Risk Level:\*\* High



\*\*Potential Consequences:\*\*

\- Unauthorized administrative actions

\- Access to restricted information

\- Unauthorized modification of application data



\*\*Recommended Controls:\*\*

\- Server-side authorization

\- Role-based access control

\- Least privilege

\- Explicit permission checks

\- Deny-by-default policies



\---



\## Risk Treatment Strategy



The recommended treatment strategy is to reduce high-priority risks through preventive and detective security controls.



\### High Risks



High risks should receive priority during security design and remediation.



Primary controls include:



\- Strong authentication

\- Authorization enforcement

\- Secure session management

\- Input validation

\- Data protection

\- Secure database access



\### Medium Risks



Medium risks should be addressed through appropriate application controls and monitoring.



Primary controls include:



\- Security logging

\- Rate limiting

\- Resource monitoring

\- Request restrictions



\---



\## Residual Risk



Even after implementing recommended controls, some level of residual risk may remain.



Residual risk should be reviewed periodically as application functionality, architecture, dependencies, and threat conditions change.



\## Risk Review Recommendations



The risk register should be reviewed when:



\- New application functionality is introduced

\- Authentication or authorization logic changes

\- Database architecture changes

\- New external services are integrated

\- Significant vulnerabilities are discovered

\- Security incidents occur

