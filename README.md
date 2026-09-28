# Security research PoC — not a real attack

This repository hosts a proof-of-concept page for a HackerOne report filed
against Elastic's `elastic/synthetics-recorder` (CWE-94 code injection via
the `popupAlias` recorder-signal field).

`index.html` demonstrates the delivery step of that vulnerability: if
recorded by a vulnerable version of Synthetics Recorder, it forges a
recorder action via the exposed `window.__pw_recorderRecordAction` API.
The payload only writes a small, timestamped, non-destructive marker file
to the OS temp directory — proof of execution, nothing more.

This page has no effect on any browser or website that isn't running
Synthetics Recorder in recording mode against it. It is not malware, not a
phishing page, and does nothing to a normal visitor.

Full writeup, root-cause analysis, and additional evidence: see the linked
HackerOne report.
