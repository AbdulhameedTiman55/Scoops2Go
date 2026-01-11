# Security Findings — Scoops2Go

This document summarises the **security-related findings** identified during
Week 8 security testing activities for Coursework 2 (2CWK70).

Testing was performed using a combination of **manual security code review**
and **exploratory endpoint testing**, with findings mapped to the
**OWASP Top 10 (2025)**.

---

## Security Testing Approach

The following approaches were used:
- Manual review of API behaviour and error handling
- Manual testing of API endpoints using a web browser
- Analysis of HTTP status codes and error responses

These techniques helped identify security weaknesses related to robustness
and exception handling.

---

## Security Findings Summary

| Finding ID | Description | OWASP Category | Severity | Status | Related Defect |
|-----------|------------|---------------|----------|--------|----------------|
| S-001 | API returns HTTP 500 for invalid endpoint | A10 – Mishandling of Exceptional Conditions | High | Open | D-API-001 |

---

## Finding Details

### S-001 — Mishandling of Exceptional Conditions

**Description:**  
A GET request to an invalid endpoint (`/products`) returned an HTTP 500
Internal Server Error instead of a safe 404 response. This behaviour exposes
internal error handling details and may assist attackers in understanding
system internals.

**OWASP Mapping:**  
A10:2025 – Mishandling of Exceptional Conditions

**Impact:**  
Improper error handling can reveal internal system behaviour and reduce the
overall robustness of the application.

**Recommendation:**  
Implement consistent exception handling to return appropriate HTTP status
codes (e.g. 404 Not Found) with user-friendly error messages.

**Status:**  
Open

---

## Conclusion

Security testing identified weaknesses related to error handling and
robustness. Although no direct data compromise was observed, improving
exception handling would enhance the security posture and resilience of the
Scoops2Go API.

These findings complement the functional defect reports and demonstrate an
awareness of secure software development practices.

