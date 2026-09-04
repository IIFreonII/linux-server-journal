Day 4: Process Management & Troubleshooting
1. Monitoring Processes

    Used htop (an improved version of top) for real-time monitoring of CPU, RAM, and process lists.
    Used ps aux to get a static snapshot of all running processes, filtered with grep (e.g., ps aux | grep ssh).
    Used pgrep <process_name> to quickly get only the PIDs of specific processes.

2. Killing Processes

    kill <PID>: Sends a SIGTERM signal, politely asking the process to shut down.
    kill -9 <PID>: Sends a SIGKILL signal, forcefully terminating a hung/unresponsive process.
    killall <name>: Kills all processes matching a specific name.

3. Lab: CPU Hog Troubleshooting

    Created a bash script with an infinite while loop to simulate a CPU-hogging process.
    Ran it in the background (./script &).
    Identified the high CPU usage and PID using htop.
    Terminated the process using kill -9.

4. Process Priorities (nice and renice)

    Linux process priorities range from -20 (highest) to +19 (lowest).
    Started a process with the lowest priority to prevent it from impacting system performance: nice -n 19 ./script.