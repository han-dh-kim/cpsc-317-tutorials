# Tutorial 2 Teaching Guide

## Preparation

- Read the [official tutorial material](https://pages.github.students.cs.ubc.ca/cpsc317/site/tutorials/1/).
- Read `tutorial_2` in the [shared Google Drive](https://drive.google.com/drive/folders/1gN4XpJVkrRdUYh8Xq5RmTiFIr8IjG44e?usp=sharing).
- Read the [Java Socket Tutorial](https://docs.oracle.com/javase/tutorial/networking/sockets/).
- Run the Echo and dictionary test demos below before class.
- Test the Wireshark demo.

## Notes

- `demo/dictionary` matches the PA1 starter code shown in the slides. It is supposed to show a `Not implemented` error.
- The official tutorial also has a PA1 code reading activity and optional tests that are not in the slides. Use them if there is extra time.

## Demo

### Echo Demo

From `tutorial_2/demo/echo`:

1. Compile the files:

   ```bash
   javac EchoServer.java EchoClient.java
   ```

2. Start the server in one terminal:

   ```bash
   java EchoServer 5000
   ```

3. Start the client in another terminal:

   ```bash
   java EchoClient localhost 5000
   ```

Type a message in the client and show that the server sends it back.

### Dictionary Test Demo

- Open `DictionaryConnectionTest.java` and show `testGetDefinition()`.
- Point out the setup, the call to `getDefinitions()`, and the final assertion.
- From `tutorial_2/demo/dictionary`, run:

  ```bash
  mvn -Dtest=DictionaryConnectionTest#testGetDefinition test
  ```

- The test should fail with `DictConnectionException: Not implemented`. This is expected because `DictionaryConnection` is still starter code.

## Timeline

| Time | Slides | Section | What to do |
|---|---:|---|---|
| 0:00–0:03 | 1–2 | Overview | Go over the tutorial topics. |
| 0:03–0:12 | 3–17 | Programming Assignment 1 | Review the dictionary service and show what students need to implement for PA1. |
| 0:12–0:20 | 18–21 | Sockets and Demo: EchoClient & EchoServer | Review Java sockets. Run the demo and give students time to try it. |
| 0:20–0:28 | 22–25 | Exercise 1: Read EchoClient's Code | Let students answer the three code reading questions, then show the answers. |
| 0:28–0:35 | 26–39 | Debugging | Explain the possible bugs and network failures shown in the slides. |
| 0:35–0:43 | 40–41 | Debugging: Writing Tests - getDefinitions() | Show `testGetDefinition()`, run it, then give students time to write a test. |
| 0:43–0:49 | 42 | Demo: Wireshark | Show how to filter `tcp.port == 2628` and follow the TCP stream. |
| 0:49–0:50 | — | Wrap-up | Take questions. |
