# Tutorial 4 Teaching Guide

## Preparation

- Read the [official tutorial material](https://pages.github.students.cs.ubc.ca/cpsc317/site/tutorials/dns/).
- Read `tutorial_4` in the [shared Google Drive](https://drive.google.com/drive/folders/1gN4XpJVkrRdUYh8Xq5RmTiFIr8IjG44e?usp=sharing).
- Skim [RFC 1035](https://datatracker.ietf.org/doc/html/rfc1035) and the [DNS Primer](https://courses.cs.duke.edu/fall16/compsci356/DNS/DNS-primer.pdf).
- Review the Java documentation for [ByteBuffer](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/nio/ByteBuffer.html) and [DatagramSocket](https://docs.oracle.com/javase/7/docs/api/java/net/DatagramSocket.html).
- Test the three `dig` commands on Slide 46 before class.
- Test the UDP echo activity below before class.

## Notes

- The original iterative-query activity uses `radicalbeerfaction.tripod.com`, but that domain is no longer available. The slides use `gaia.cs.umass.edu` instead. The exact DNS output may change. Focus on how each response gives the next nameserver.
- `demo/udp-echo/EchoClient.java` is starter code. Its `ping()` method returns `null` until students implement it. Slide 49 has the solution.
- The official tutorial also has a short section on testing PA2 code that is not in the slides. Use it if there is extra time.

## Activity

### UDP Echo Activity

From `tutorial_4/demo/udp-echo`:

1. Open `EchoClient.java` and give students time to implement `ping()`.

2. Compile the server and client after students finish:

   ```bash
   make
   ```

   If `make` is unavailable, run:

   ```bash
   javac EchoServer.java EchoClient.java
   ```

3. Start the server in one terminal:

   ```bash
   java EchoServer 5000
   ```

4. Start the client in another terminal:

   ```bash
   java EchoClient localhost 5000
   ```

If the implementation is correct, the client should print:

```text
Received: hello 0
Received: hello 1
...
Received: hello 9
```

Show the solution on Slide 49 after students have tried the activity. Stop the server with `Ctrl+C` when finished.

## Timeline

| Time | Slides | Section | What to do |
|---|---:|---|---|
| 0:00–0:03 | 1–2 | Overview | Go over the tutorial topics and how they connect to PA2. |
| 0:03–0:07 | 3–17 | PA1 and PA2 | Compare the DICT client with the DNS client. Explain the change from TCP to UDP and why PA2 may contact multiple servers. |
| 0:07–0:11 | 18–19 | DNS Vocabulary | Review A, AAAA, CNAME, and NS records, then read the example records with the class. |
| 0:11–0:17 | 20–25 | DNS Messages | Explain the five message sections. Give students time to answer the question on Slide 21, then show the answers. |
| 0:17–0:26 | 26–32 | ByteBuffer Activity | Explain content and position. Let students answer each question before showing the answer slide. |
| 0:26–0:38 | 33–46 | Iterative DNS Queries | Let students follow the referrals with `dig`. Explain how the Authority and Additional sections tell them which server to query next. |
| 0:38–0:49 | 47–49 | UDP Sockets in Java | Review `DatagramSocket`, then give students time to implement `ping()`. Show the solution after they try it. |
| 0:49–0:50 | — | Wrap-up | Take questions and remind students how the activities map to PA2. |
