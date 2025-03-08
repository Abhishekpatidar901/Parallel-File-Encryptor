# Parallel File Encryptor

## Overview

This project demonstrates the implementation of encryption and decryption mechanisms using parallel processing techniques in C++. By leveraging both multiprocessing and multithreading, the project aims to enhance the efficiency and performance of cryptographic operations.

## Aproaches

The repository contains three folders, each dedicated to a distinct parallel processing approach.

### 1. `Queue based Multiprocessing parallel file encryptor`

**Description:** This showcases the use of parallel multiprocessing by creating child processes to handle encryption and decryption tasks. It utilizes the `fork()` system call to spawn child processes, enabling concurrent execution of tasks.

**Key Features:**

- **Process Management:** Implements process creation and management using `fork()`.
- **Task Queue:** Manages encryption and decryption tasks using a queue structure.
- **Task Execution:** Child processes execute tasks independently, allowing parallel processing.

### 2. `SharedMemory based multiprocessing parallel file encryptor`

**Description:** This showcases the use of parallel multiprocessing by creating child processes to handle encryption and decryption tasks. It utilizes shared memory segments for efficient inter-thread communication. It employs semaphores to manage synchronization and ensure data consistency, and locks to prevent concurrent access.

**Key Features:**

- **Process Management:** Implements process creation and management using `fork()`.
- **Shared Memory:** Utilizes shared memory for communication between threads.
- **Task Execution:** Child processes execute tasks independently, allowing parallel processing.
- **Semaphores and locks:** Employs semaphores to manage synchronization and ensure data consistency.

### 3. `Multithreading based parallel file encryptor`

**Description:** This branch focuses on multithreading combined with shared memory to perform encryption and decryption. It employs POSIX threads (`pthread`) and utilizes shared memory segments for efficient inter-thread communication.

**Key Features:**

- **Multithreading:** Implements concurrent execution using POSIX threads.
- **Shared Memory:** Utilizes shared memory for communication between threads.
- **Semaphores and locks:** Employs semaphores to manage synchronization and ensure data consistency.

The Multithreading-based encryptor is the fastest and most efficient due to lower overhead in context switching and memory usage. While Queue-based and SharedMemory-based multiprocessing provide true parallelism, they incur higher process creation and synchronization costs. Multithreading efficiently utilizes shared memory with minimal overhead, making it ideal for performance-sensitive tasks.

## Getting Started

To explore the implementations:

   ```bash
   git clone <repo-url>
   cd Parallel file encryptor
    # different path for different approaches
   cd path 
   # Now make a virtual env and activate and use scripts for generating test files
   python -m venv /myvenv
   source myvenv/bin/activate
   python makeDirs.py
   make
   ./encrypt_decrypt
   # type directory name which is created from makeDirs.py
   test
   ENCRYPT # after giving directory name, give ENCRYPT or DECRYPT to tell what to do
   ```
