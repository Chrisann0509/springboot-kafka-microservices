## 1. Download Kafka

[Quickstart](https://kafka.apache.org/quickstart/)

## 2. Step-by-Step: Starting Kafka

### Step 1: Navigate to Kafka directory

```bash
cd C:\Users\Hp\Documents\kafka\kafka_2.13-4.1.1
```

### Step 2: Generate a Cluster ID

```bash
bin\windows\kafka-storage.bat random-uuid
```

Example output:

```
ERROR Reconfiguration failed: No configuration found for '3cd1a2f1'
4vRGSS-eQ5S7FQ_qWvLaiQ
```

✅ **The UUID is valid**

⚠️ The error message is **harmless Windows Log4j noise** and can be ignored.

### Step 3: Format Kafka Storage (Standalone Mode)

Kafka requires storage formatting before first startup.

```bash
bin\windows\kafka-storage.bat format --standalone -t vjj67CgCTH-mU8BKnNkErw -c config\server.properties
```

Expected output:

```
Formatting dynamic metadata voter directory /tmp/kraft-combined-logs
```

✅ This means formatting succeeded.

### Step 4: Start Kafka Server

```bash
bin\windows\kafka-server-start.bat config\server.properties
```

Successful startup log:

```
KafkaServer id=1 started
```
