# Tutorial 6 Teaching Guide

## Preparation

- Read the [official tutorial material](https://pages.github.students.cs.ubc.ca/cpsc317/site/tutorials/SocketInC/).
- Read `tutorial_6` in the [shared Google Drive](https://drive.google.com/drive/folders/1gN4XpJVkrRdUYh8Xq5RmTiFIr8IjG44e?usp=sharing).
- Read Section [6.1: A Simple Stream Server](https://beej.us/guide/bgnet/html/split/client-server-background.html) of Beej's Guide, starting at `main()`.
- Read the Synopsis and Description sections of the [pthread_create()](https://man7.org/linux/man-pages/man3/pthread_create.3.html) and [pthread_join()](https://man7.org/linux/man-pages/man3/pthread_join.3.html) man pages.
- Download the [starter code](https://pages.github.students.cs.ubc.ca/cpsc317/site/tutorials/assets/SocketInC/starterSum26.c) and [answer](https://pages.github.students.cs.ubc.ca/cpsc317/site/tutorials/assets/SocketInC/answerSum26.c) for the PThreads activity.

## Notes

- Beej's server example uses `fork()` to create child processes. It does not use PThreads. Keep this distinction clear when moving to Exercise 2.
- The socket code on Slides 21 and 29 shows the basic flow, not complete programs. Real code must check return values and handle partial sends and receives. See [Beej's send() and recv() explanation](https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html).

## Timeline

| Time | Slides | Section | What to do |
|---|---:|---|---|
| 0:00–0:02 | 1–2 | Overview | Go over the tutorial topics and how they connect to PA3. |
| 0:02–0:05 | 3–10 | Introduction to PA3 | Compare the TCP client in PA1 and UDP client in PA2 with the TCP server students will implement in C. |
| 0:05–0:08 | 11–12 | File Descriptors | Explain that a socket fd is an integer used to identify an open socket, not a C pointer. |
| 0:08–0:19 | 13–22 | TCP Server in C | Go through the server's socket calls. Distinguish the listening fd from `client_fd`. Use Slide 21 to explain `getaddrinfo()` and initializing `addrlen` before `accept()`. |
| 0:19–0:24 | 23–29 | TCP Client in C | Compare the client with the server. Explain `connect()` and review the complete sequence on Slide 29. |
| 0:24–0:32 | 30 | Exercise 1: Beej's TCP Socket Code | Let students read from `main()` and identify the socket setup and connection-handling steps. Walk around and help, then review the main calls together. |
| 0:32–0:38 | 31–35 | PThreads in C | Explain why a server may need threads. Introduce the exercise on Slide 32, then go through the basic example on Slide 33 before students start coding. |
| 0:38–0:42 | 32 | Exercise 2: Part 1 | Let students create 50 threads to run `runTask()`. Explain how each thread receives its task ID. |
| 0:42–0:49 | 32 | Exercise 2: Part 2 | Let students run the 50 tasks in groups of 10. Check that each group finishes before the next starts, then review the answer. |
| 0:49–0:50 | — | Wrap-up | Take questions. |
