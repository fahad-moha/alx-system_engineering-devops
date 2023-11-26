# Processes and signals

1. PID (Process ID):
PID stands for Process ID. It is a unique numerical identifier assigned to each running process in an operating system. PIDs are used by the operating system to track and manage processes.

2. Process:
A process is an instance of a computer program that is being executed. It is an active entity that performs specific tasks or operations within an operating system. Each process has its own memory space and resources.

3. How to find a process' PID:
To find a process' PID, you can use various system tools and commands depending on the operating system:

- On Unix-like systems (Linux, macOS, etc.), you can use the `ps` command with options to list running processes and their PIDs. For example:
  ````bash
  ps -ef | grep <process_name>
  ```

- On Windows, you can use the `tasklist` command to list running processes and their PIDs. For example:
  ````cmd
  tasklist | findstr <process_name>
  ```

4. How to kill a process:
To kill a process, you can use the `kill` command (or `killall` on some systems) along with the process' PID. The command sends a signal to the process, requesting it to terminate. The process can handle the signal and perform cleanup operations before exiting.

- On Unix-like systems, you can use the `kill` command followed by the PID of the process. For example:
  ````bash
  kill <PID>
  ```

- On Windows, you can use the `taskkill` command followed by the PID of the process. For example:
  ````cmd
  taskkill /PID <PID>
  ```

5. Signal:
A signal is a software interrupt delivered to a process by the operating system. Signals can be used for inter-process communication, process management, and handling exceptional conditions. Signals can be sent to processes to indicate events or to request specific actions.

6. Two signals that cannot be ignored:
- SIGKILL (signal number 9): This signal is used to forcefully terminate a process. It cannot be caught or ignored by the process. When a process receives a SIGKILL signal, it is immediately terminated without any chance to clean up or handle the signal.

- SIGSTOP (signal number 19 on most systems): This signal is used to suspend (stop) a process. It cannot be caught or ignored by the process. When a process receives a SIGSTOP signal, it is temporarily halted and put in a suspended state. It can be resumed later with a SIGCONT signal.
