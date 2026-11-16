
# MediTrack – Validation Findings and Comparison Report

**Project:** MediTrack – Online Appointment System  
**Document Reviewed:** `srs/meditrack-srs.md`  
**Checklist Version:** 0.1  
**Reviewers:** Student A (sidra) and Student B (eisha)

---

## 1. Introduction

The purpose of this report is to compare the independent validation results of Student A and Student B and identify problems in the MediTrack Software Requirements Specification (SRS).

Both students reviewed the SRS independently using the same validation checklist.

After comparing their answers, this report identifies:

- Requirements where both students agree.
- Requirements where students disagree.
- Contradictions within the SRS.
- Missing and unclear requirements.
- Risks affecting clinic operations.
- Recommended solutions for every identified problem.

---

## 2. Comparison of Student A and Student B

| Checklist ID | Student A | Student B | Comparison |
|---|---|---|---|
| C-01 | Yes | No | Disagreement |
| C-02 | No | No | Agreement |
| C-03 | No | No | Agreement |
| C-04 | No | No | Agreement |
| C-05 | No | No | Agreement |
| C-06 | No | No | Agreement |
| C-07 | No | No | Agreement |
| C-08 | No | No | Agreement |
| C-09 | No | No | Agreement |
| C-10 | No | Yes | Disagreement |
| C-11 | No | No | Agreement |
| C-12 | No | No | Agreement |
| C-13 | No | No | Agreement |
| C-14 | No | Yes | Disagreement |
| C-15 | No | No | Agreement |
| C-16 | No | No | Agreement |
| C-17 | No | No | Agreement |
| C-18 | No | No | Agreement |

### 2.1 Summary of Comparison

| Result | Total |
|---|---:|
| Agreement | 15 |
| Disagreement | 3 |
| Total Checklist Items | 18 |

### 2.2 Areas Where Both Students Agree

Both students identified the following problems:

1. R-02 does not specify a measurable response time.
2. R-03 does not explain how double bookings will be prevented.
3. R-04 and R-05 need clarification.
4. R-06 does not specify reminder timing.
5. R-06 does not specify the reminder delivery method.
6. R-07 needs clearer cancellation rules.
7. R-08 does not define accessibility requirements.
8. R-09 does not specify medical record access permissions.
9. R-10 does not explain emergency walk-in handling.
10. R-12 does not specify exact working hours.
11. R-13 does not explain overdue payment policies.
12. R-03 does not explain booking conflict validation.
13. The SRS does not address Monday morning peak demand.
14. R-07 does not clearly explain patient cancellation notifications.
15. The SRS needs clearer requirements for booking and system performance.

### 2.3 Areas Where Students Disagree

#### Disagreement 1: C-01 – Requirement Clarity

- Student A: Yes
- Student B: No

**Student A's reasoning:** All requirements have unique IDs and describe system functions or qualities.

**Student B's reasoning:** R-02 uses the vague word "quickly", and R-08 uses "user-friendly".

**Final decision:** Student B is correct for the checklist question about clear system functions or qualities. Unique IDs do not guarantee clear requirements.

**Solution:** Rewrite vague requirements using measurable and understandable language.

#### Disagreement 2: C-10 – Emergency Walk-in Handling

- Student A: No
- Student B: Yes

**Student A's reasoning:** R-10 does not explain emergency walk-in procedures.

**Student B's reasoning:** R-10 allows receptionists to book walk-in patients.

**Final decision:** Student A is correct. Supporting ordinary walk-in bookings does not necessarily cover emergency cases.

**Solution:** Add a separate requirement defining emergency walk-in handling and prioritization.

#### Disagreement 3: C-14 – Doctor Schedule Information

- Student A: No
- Student B: Yes

**Student A's reasoning:** R-14 does not specify what information appears in the daily schedule.

**Student B's reasoning:** R-14 clearly states that doctors can view their daily schedules.

**Final decision:** Both interpretations are reasonable. The answer depends on the checklist question. R-14 does allow doctors to view daily schedules, but does not specify the schedule details.

**Solution:** Define the information doctors can view, such as appointment time, patient name, and appointment status, subject to privacy permissions.

---

## 3. Contradictions and Inconsistencies in the SRS

A contradiction occurs when two requirements conflict with each other or when their meaning is inconsistent.

### Contradiction 1: R-04 and R-05 – Appointment Duration

**R-04:**
Each appointment shall last 15 minutes.

**R-05:**
The system shall allow doctors to set appointment length between 10 and 30 minutes.

**Problem:**

R-04 says every appointment must last exactly 15 minutes, while R-05 allows different appointment durations between 10 and 30 minutes.

These requirements are inconsistent unless 15 minutes is intended to be the default duration.

**Solution:**

Clarify that 15 minutes is the default appointment duration and authorized doctors can change it between 10 and 30 minutes.

**Suggested revised requirements:**

- R-04: The system shall use 15 minutes as the default appointment duration.
- R-05: The system shall allow authorized doctors to configure appointment durations between 10 and 30 minutes.

### Inconsistency 2: R-08 – User-Friendly for All Age Groups

**Problem:**

R-08 states that the system must be user-friendly for all age groups but does not specify measurable accessibility features.

**Solution:**

Add specific accessibility requirements, such as:

- Readable text sizes.
- Simple navigation.
- Clear error messages.
- Accessible booking options.

### Inconsistency 3: R-09 – Secure Patient Records

**Problem:**

R-09 requires secure patient records but does not define how security will be achieved.

**Solution:**

Specify authentication, encryption, and role-based access permissions.

### Inconsistency 4: R-12 – Normal Working Hours

**Problem:**

R-12 says the system must be available during normal working hours but does not define those hours.

**Solution:**

Specify exact working days and operating times, including any applicable holiday arrangements.

---

## 4. Complete Findings and Solutions

| Finding ID | Requirement ID | Identified Problem | Severity | Proposed Solution |
|---|---|---|---|---|
| F-01 | R-02 | Response time is vague. | High | Set a measurable response-time target, such as 2 seconds under normal load. |
| F-02 | R-03 | Double-booking prevention is not explained. | Critical | Define conflict checking and atomic booking confirmation. |
| F-03 | R-04, R-05 | Appointment durations are inconsistent. | High | Make 15 minutes the default and allow authorized doctors to change it between 10 and 30 minutes. |
| F-04 | R-06 | Reminder timing is missing. | High | Define reminders, such as 24 hours before appointments. |
| F-05 | R-06 | Reminder delivery method is missing. | Medium | Specify SMS, email, or other supported channels. |
| F-06 | R-07 | Cancellation policy is unclear. | Medium | Define cancellation rules and schedule update procedures. |
| F-07 | R-07 | Receptionist notification method is missing. | Medium | Specify an in-system notification or another defined method. |
| F-08 | R-08 | Accessibility for elderly patients is not defined. | High | Add readable text, simple navigation, and accessibility features. |
| F-09 | R-09 | Security controls are not specified. | Critical | Define encryption, authentication, and access controls. |
| F-10 | R-09 | Medical record permissions are missing. | Critical | Define permissions for each authorized user role. |
| F-11 | R-10 | Emergency walk-in handling is missing. | High | Define emergency procedures and clinical prioritization. |
| F-12 | R-12 | Working hours are unclear. | Medium | Specify exact availability days and times. |
| F-13 | R-13 | Overdue payment policy is not described. | Medium | Document the clinic's payment rules and procedures. |
| F-14 | R-14 | Daily schedule information is not defined. | Medium | Specify what appointment details doctors can view. |
| F-15 | Missing | Monday morning peak demand is not addressed. | High | Define peak-load performance requirements. |
| F-16 | Missing | Concurrent booking capacity is not specified. | High | Define expected simultaneous users and booking requests. |
| F-17 | R-11 | Active appointment meaning is unclear. | Medium | Define whether pending, cancelled, and completed appointments count toward the limit. |

---

## 5. Main Clinic Risks and Their Solutions

### Risk 1: Double Bookings

**Related Requirement:** R-03

**Problem:** Two patients may book the same doctor's time slot.

**Solution:** The system must check availability before confirming a booking and prevent overlapping appointments, including simultaneous booking requests.

### Risk 2: Patients Forget Appointments

**Related Requirement:** R-06

**Problem:** Patients may forget their appointments, causing financial losses.

**Solution:** Send automated reminders at defined intervals through SMS or email.

### Risk 3: Medical Information Exposure

**Related Requirement:** R-09

**Problem:** Unauthorized users may access confidential patient records.

**Solution:** Implement authentication, encryption, and role-based access controls.

### Risk 4: Elderly Patients Being Excluded

**Related Requirement:** R-08

**Problem:** Elderly patients may struggle with complicated online booking.

**Solution:** Provide accessible interfaces, readable text, simple navigation, and receptionist-assisted booking.

### Risk 5: Emergency Walk-in Delays

**Related Requirement:** R-10

**Problem:** Emergency patients may not receive appropriate priority.

**Solution:** Define emergency escalation procedures and allow clinical staff to prioritize patients according to urgency.

### Risk 6: Monday Morning System Overload

**Related Requirement:** R-02

**Problem:** High booking demand may cause slow responses or booking failures.

**Solution:** Define load-testing targets, concurrent-user capacity, and system performance limits.

---

## 6. Final Agreed Recommendations

After comparing the two reviews, the following improvements are recommended:

1. Rewrite vague requirements in measurable terms.
2. Resolve the appointment duration conflict between R-04 and R-05.
3. Define double-booking prevention.
4. Specify reminder timing and notification methods.
5. Clarify cancellation rules and notifications.
6. Add accessibility requirements for elderly patients.
7. Define medical record security and role permissions.
8. Add emergency walk-in procedures.
9. Define exact system working hours.
10. Document overdue payment policies.
11. Specify Monday morning performance requirements.
12. Define concurrent booking capacity.
13. Clarify the meaning of active appointments.
14. Define the information shown in doctors' daily schedules.

---

## 7. Final Conclusion

The independent reviews by Student A and Student B identified several weaknesses in the MediTrack SRS.

The students agreed on 15 checklist answers and disagreed on 3 answers. The disagreements were discussed, and final decisions were recorded.

The most serious issues are double-booking prevention, medical information security, and the inconsistency between R-04 and R-05.

The SRS also lacks important details concerning reminders, emergency walk-ins, accessibility, and Monday morning performance.

**Final Decision: Revision Required Before Approval.**

The software company should resolve the identified problems, update the SRS, and submit it for another validation review before the clinic signs the contract.

