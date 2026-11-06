# Actionable Canvas output

`classify_event` returns keep, skip or needs_review. Announcements, holidays, attendance and class-information events are not tasks. Homework, projects, quizzes, exams and other explicit action titles are tasks. Existing course-specific CS announcement and MATH duplicate rules remain documented in the owning repository. Unknown titles must be classified rather than silently forwarded.

The rolling date window is enforced before semantic cache lookup, and expired cache entries are pruned. Exact current patterns live beside the parser and are explained in the feed repository's filtering documentation.
