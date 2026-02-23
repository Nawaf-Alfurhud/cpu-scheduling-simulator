# cpu-scheduling-simulator
Java-based simulator for classic **operating system CPU scheduling**.  
Implements **FCFS**, **Round Robin**, and **Priority Scheduling**, using **PCBs**, synchronized queues, and an execution log to trace what happens to each process.

## What’s inside
- **Scheduling algorithms**
  - FCFS (First Come, First Served)
  - Round Robin (time-sliced)
  - Priority Scheduling (+ simple starvation detection)
- **Core OS concepts**
  - `PCB` (Process Control Block) representation
  - `ProcessQueue` for job/ready queues
  - `JobReader` + `Loader` to admit jobs into the system
  - `ExecutionLog` to record state transitions / events
  - `SysCall` to simulate OS-style operations

## Project Structure
- `Main.java` — runs the simulation and selects the scheduling policy
- `job.txt` — input job list used by the simulator
- `PCB.java` — process metadata/state
- `ProcessQueue.java` — queue abstraction used by schedulers/loader
- `JobReader.java` — reads job definitions from `job.txt`
- `Loader.java` — loads/admit jobs into the system
- `ExecutionLog.java` — logs execution events / transitions
- `SysCall.java` — helper layer for simulated system operations

## Input Format (`job.txt`)
This project expects a `job.txt` file in the **same folder** as `Main.java` in the following format
<ID>:<burstTime>:<priority>;<memoryRequired>
