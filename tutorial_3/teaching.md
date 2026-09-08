# Tutorial 3 Teaching Guide

## Preparation

- Read the [official tutorial material](https://pages.github.students.cs.ubc.ca/cpsc317/site/tutorials/2/).
- Read `tutorial_3` in the [shared Google Drive](https://drive.google.com/drive/folders/1gN4XpJVkrRdUYh8Xq5RmTiFIr8IjG44e?usp=sharing).
- Read Sections [2.4](https://www.rfc-editor.org/rfc/rfc2229#section-2.4) and [3.5.1](https://www.rfc-editor.org/rfc/rfc2229#section-3.5.1) of RFC 2229.
- Review the [Java Socket Tutorial](https://docs.oracle.com/javase/tutorial/networking/sockets/) if needed.
- Run the netcat server demo below before class.

## Notes

- Give students time to answer the questions on Slides 11, 15, 20, and 25 before showing the answers.
- Slides 30–33 review socket programming from Tutorial 1. Keep this part short if you are running out of time.
- The official tutorial has more notes on connection handling than the slides. If time, remind students to handle connection errors, malformed responses, complete multi-line responses, and proper connection termination.

## Demo

### Netcat Server Demo

From `tutorial_3/demo/netcat`:

1. Start the server:

   ```bash
   nc -l 2628 < server_responses.txt
   ```

2. Run the PA1 client using `localhost` and port `2628`.

The sample file includes the welcome message, the `SHOW DB` response, and the `SHOW STRAT` response in the order expected by the client.

Some versions of netcat need `nc -l -p 2628`. Windows uses `ncat` instead of `nc`.

## Timeline

| Time | Slides | Section | What to do |
|---|---:|---|---|
| 0:00–0:04 | 1–2 | Overview | Go over the tutorial topics. |
| 0:04–0:08 | 3–8 | Programming Assignment 1 | Review how PA1 connects to the dictionary service and what students need to implement. |
| 0:08–0:18 | 9 | Exercise 1: Using netcat server | Show the demo, then give students time to start a server and connect their PA1 client. |
| 0:18–0:22 | 10 | Tutorial 1: Online Dictionaries | Let students answer the four review questions with netcat. |
| 0:22–0:36 | 11–24 | Exercise 2: Reading RFC 2229 | Let students answer the status code questions, then show the answers. |
| 0:36–0:40 | 25–26 | Exercise 2: SHOW DB | Explain the two responses and the single-dot terminator. |
| 0:40–0:44 | 27–29 | DIY: Map Methods to RFC Commands | Let students map each PA1 method to a DICT command, then review the answers. |
| 0:44–0:49 | 30–33 | Socket Programming in Java | Review the client and server code. Explain blocking calls and when to stop reading. |
| 0:49–0:50 | — | Wrap-up | Take questions. |
