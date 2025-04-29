# smart_meter_io.py
# Demonstrates use of file handling functions for smart meter readings
# Covers: open(), read(), readline(), readlines(), write(), writelines(), close()

# Sample smart meter data
readings = [
    "MeterID: 101, Usage: 45.6 kWh, Time: 2025-04-29 10:00\n",
    "MeterID: 102, Usage: 30.2 kWh, Time: 2025-04-29 11:00\n",
    "MeterID: 103, Usage: 55.8 kWh, Time: 2025-04-29 12:00\n"
]

# --- Writing data to file using write() and writelines() ---
fh = open("smart_readings.txt", "w")
fh.write("Smart Meter Data:\n")         # Write header
fh.writelines(readings)                # Write list of readings
fh.close()

# --- Reading entire file content using read() ---
fh = open("smart_readings.txt", "r")
content = fh.read()
print("Using read():\n", content)
fh.close()

# --- Reading one line at a time using readline() ---
fh = open("smart_readings.txt", "r")
line = fh.readline()
print("Using readline():", line.strip())  # Reads the first line
fh.close()

# --- Reading all lines into a list using readlines() ---
fh = open("smart_readings.txt", "r")
lines = fh.readlines()
print("Using readlines():")
for l in lines:
    print(l.strip())
fh.close()

# --- Appending new reading using append mode and write() ---
fh = open("smart_readings.txt", "a")
fh.write("MeterID: 104, Usage: 40.0 kWh, Time: 2025-04-29 13:00\n")
fh.close()
