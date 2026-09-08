# Tutorial 1 Teaching Guide

## Preparation

- Read the [official tutorial material](https://pages.github.students.cs.ubc.ca/cpsc317/site/tutorials/0/).
- Read `tutorial_1` in the [shared Google Drive](https://drive.google.com/drive/folders/1gN4XpJVkrRdUYh8Xq5RmTiFIr8IjG44e?usp=sharing).
- Skim [RFC 2229](https://www.rfc-editor.org/rfc/rfc2229) and [RFC 959](https://www.rfc-editor.org/rfc/rfc959).
- Read the [Java Socket Tutorial](https://docs.oracle.com/javase/tutorial/networking/sockets/).
- Edit the introduction on Slide 2.
- Check and update the Tutorial Logistics on Slide 4.
- Test `nc` with `dict.org`, `ftp.cs.wisc.edu`, and `example.com` before class.
- Run the Knock Knock demo below before class.

## Notes

- Tutorial 1 is context-heavy, so you may run out of time. To stay on schedule:
  - Don't install WSL during the tutorial. It can take over 20 minutes. Use the undergraduate Linux servers instead.
  - Give students enough time for Exercises 1–3. Keep Exercise 4 short, and use Exercise 5 as a preview.

## Demo

### Knock Knock Demo

From `tutorial_1/demo/knock-knock`:

1. Compile the files:

   ```bash
   javac KnockKnockServer.java KnockKnockClient.java KnockKnockProtocol.java
   ```

2. Start the server in one terminal:

   ```bash
   java KnockKnockServer 5000
   ```

3. Start the client in another terminal:

   ```bash
   java KnockKnockClient localhost 5000
   ```

Follow the prompts in the client to complete the joke.

## Timeline

| Time | Slides | Section | What to do |
|---|---:|---|---|
| 0:00–0:05 | 1–5 | Introduction, Tutorial Logistics, and Overview | Introduce yourselves and go over the tutorial format. |
| 0:05–0:10 | 6 | Preparation: netcat | Give students five minutes to get netcat or SSH working. Walk around and help. |
| 0:10–0:22 | 7–29 | Exercise 1: Online Dictionaries | Go through the netcat diagrams. Give students time to answer the questions, then show the answers. |
| 0:22–0:30 | 30–33 | Exercise 2: Connecting to the FTP Service | Let students run the FTP commands and set up the passive connection. Walk around and help. |
| 0:30–0:38 | 34–40 | Exercise 3: Connecting to a Web Server | Let students try an invalid HTTP request, then a valid one. Explain CRLF and the blank line. |
| 0:38–0:43 | 41–44 | Exercise 4: Other useful network tools | Briefly explain each tool. |
| 0:43–0:48 | 45–49 | Exercise 5: Socket programming in Java | Give a short introduction to sockets and the Knock Knock example. |
| 0:48–0:50 | — | Wrap-up | Take questions. |
