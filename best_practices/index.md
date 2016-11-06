---
---

# Best Practices
{% capture tmp %}{% increment bpCount %}{% endcapture %}

------

### Best Practice #{% increment bpCount %} – Use of Objectives

(Since Objectives usage outside of course structure is not defined.)

Objectives are defined for the course structure, but there is no language in the specification concerning their usage in statements. If using Objectives in statements (as Activities) the best practice is to use the Activity Definition type (http://adlnet.gov/expapi/activities/objective) from the ADL vocabulary.

The same Objective can be referenced by multiple AU or Blocks. There are 2 ways to interpret meeting an Objective. The two expected practices are:

1. All elements referencing the Objective need to be Satisfied (or met moveOn criteria)
1. Only one element referencing the Objective needs to be Satisfied (or met moveOn criteria).

It is recommended that LMS developers document how they do this and allow for an extension (in the course structure) to indicate what method should be used.

### Best Practice #{% increment bpCount %} – LMS should always implement the "returnURL"

LMS should always implement the "returnURL"

LMS should not spawn a new window to launch AU (i.e. “popup”). Depending on the settings it could take the following actions to launch an AU:

* **OwnWindow** – Redirect same window to AU location
* **AnyWindow** – Either redirect same window or use iFrame, “LightBox”, etc.

### Best Practice #{% increment bpCount %} – Fetch URLs

* The Fetch URL should be unique for each session.
* Do not reuse auth tokens.

### Best Practice #{% increment bpCount %} – AU Mastery Score

If the LMS issues a Mastery Score, the AU should respond in the following ways:

* If the AU has no notion of scoring, it should not issue Passed or Failed statements.
* If the AU does not have scoring or the learner does not meet the Mastery Score then the AU must not issue a Passed Statement (per the specification).
* The AU can also refuse to execute because the Mastery Score issued is inconsistent with the learning design of the AU. In this situation, the AU should inform the learner why it cannot execute.

### Best Practice #{% increment bpCount %} – LMS Mastery Score

LMS should use caution when adding Mastery Scores to AU course structure entries if they are not present in the original course structure. (As the AU may not be designed to handle scores). It is recommended that such changes be tested prior to enrolling learners.

### Best Practice #{% increment bpCount %} – Always specify a moveOn criterion in the course structure for each AU

When creating a course structure, always specify a moveOn criteria for each AU. Failing to do so will result in a default of “Not Applicable”. This can have the following unintended consequences:

* When failing to specify moveOn criteria or specifying “NotApplicable” as the moveOn criteria for all AU’s in a course, the course will automatically being marked satisfied immediately upon registration of the learner (before the learner launches a single AU).
* If at least one AU has a moveOn criteria specified (other than “NotApplicable”) then the course would be satisfied upon satisfaction of those AU’s.
* It is considered to be a better practice to explicitly specify the moveOn for each AU in a course structure to ensure there is no confusion over the satisfaction requirements of a course.

------
