# Tutorial 5 Teaching Guide

## Preparation

- Read the [official tutorial material](https://pages.github.students.cs.ubc.ca/cpsc317/site/tutorials/dns2/).
- Read `tutorial_5` in the [shared Google Drive](https://drive.google.com/drive/folders/1gN4XpJVkrRdUYh8Xq5RmTiFIr8IjG44e?usp=sharing).
- Read Section [4.2.2: TCP usage](https://datatracker.ietf.org/doc/html/rfc1035#section-4.2.2) of RFC 1035.
- Review the DNS trace on Slides 4–13 and `getResultsFollowingCNames()` in the PA2 starter code.

## Notes

- The trace on Slides 4–13 comes from a fully implemented PA2 client. Use the output in the slides for this activity. Students may not be able to reproduce it with their unfinished code.
- The `radicalbeerfaction.tripod.com` example no longer works. Use the recorded CNAME chain on Slide 19 to trace the code instead of running the queries live.

## Timeline

| Time | Slides | Section | What to do |
|---|---:|---|---|
| 0:00–0:03 | 1–2 | Overview | Go over the tutorial topics. |
| 0:03–0:07 | 3 | Resolving a Nameserver | Introduce the case where an NS record has no IP address in the Additional section. Explain the PA2 commands and how to read a query line. |
| 0:07–0:18 | 4–13 | Resolving a Nameserver: Example | Go through the trace. Let students work out what to query when the Additional section is empty, then show how resolving `ns2.google.com` lets us continue the lookup for `finance.google.ca`. |
| 0:18–0:28 | 14–18 | Tracing getResultsFollowingCNames() | Read the function with the class. Explain the indirection limit, the direct-answer case, and the recursive CNAME call. |
| 0:28–0:35 | 19–20 | Example CNAME Chain | Let students trace the three calls to `iterativeQuery()`. Explain that it returns the CNAME record and `getResultsFollowingCNames()` follows the chain. |
| 0:35–0:39 | 21 | TCP Fallback | Explain the TC bit and why a truncated UDP response requires another query over TCP. |
| 0:39–0:44 | 22–23 | TCP Message Format | Let students read the RFC and answer the question, then show the answer. Explain the 2-byte length field. |
| 0:44–0:49 | 24–25 | TCP Message Activity | Let students count the bytes and work out the prefix, then show why it is `00 27`. The length excludes the prefix itself. Remind students to read the length first, then that many bytes when receiving over TCP. |
| 0:49–0:50 | — | Wrap-up | Take questions. |
