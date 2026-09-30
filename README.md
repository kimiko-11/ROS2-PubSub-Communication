
# ROS 2 Python Publisher-Subscriber

### A Minimal ROS 2 Communication Example using `rclpy`

This project demonstrates the fundamental **Publisher-Subscriber communication model in ROS 2** using Python and `rclpy`.

A publisher node sends `"Hello World"` messages to the `/chatter` topic every second, while a subscriber node listens to the same topic and displays the received messages.

This project is designed as a hands-on introduction to **ROS 2 nodes, topics, publishers, subscribers, and package structure**.

---

##  What This Project Demonstrates

- ROS 2 Python package development
- Creating ROS 2 nodes using `rclpy`
- Publisher-Subscriber communication
- ROS 2 topics
- Message publishing and subscription
- Building packages with `colcon`
- Visualizing ROS 2 communication using `rqt_graph`

---

## 📁 Project Structure

```text
py_pubsub/
├── py_pubsub/
│   ├── publisher_node.py
│   └── subscriber_node.py
│
├── images/
│   ├── publisher_output.png
│   └── rqt_graph.png
│
├── package.xml
├── setup.py
├── setup.cfg
└── README.md
````

---

##  System Architecture

```text
┌─────────────────────┐
│   minimal_publisher │
│                     │
│  Publishes messages │
└──────────┬──────────┘
           │
           │  /chatter
           │
           ▼
┌─────────────────────┐
│   minimal_subscriber │
│                     │
│ Receives messages   │
└─────────────────────┘
```

The publisher and subscriber communicate through the `/chatter` ROS 2 topic.

---

##  Nodes

| Node                 | Description                                           |
| -------------------- | ----------------------------------------------------- |
| `minimal_publisher`  | Publishes `String` messages to `/chatter`             |
| `minimal_subscriber` | Subscribes to `/chatter` and prints received messages |

### Topic

```text
/chatter
```

### Message Type

```text
std_msgs/msg/String
```

---

## ⚙️ Requirements

* Ubuntu 22.04
* ROS 2 Humble
* Python 3.10+
* `rclpy`
* `colcon`
* `rqt_graph`

> If using Windows, the project can be run through **WSL2 with Ubuntu 22.04**.

---

##  Setup

### 1. Create or navigate to the ROS 2 workspace

```bash
cd ~/ros2_ws
```

### 2. Build the package

```bash
colcon build
```

### 3. Source the workspace

```bash
source install/setup.bash
```

---

## 📡 Run the Publisher

Open a terminal and run:

```bash
cd ~/ros2_ws
source install/setup.bash

ros2 run py_pubsub talker
```

The publisher will periodically send messages to `/chatter`.

Example:

```text
Publishing: "Hello World: 1"
Publishing: "Hello World: 2"
Publishing: "Hello World: 3"
```

---

##  Run the Subscriber

Open a second terminal:

```bash
cd ~/ros2_ws
source install/setup.bash

ros2 run py_pubsub listener
```

The subscriber receives the messages:

```text
I heard: "Hello World: 1"
I heard: "Hello World: 2"
I heard: "Hello World: 3"
```

---

##  Visualizing the ROS 2 Graph

ROS 2 communication can be visualized using `rqt_graph`.

Run:

```bash
rqt_graph
```

The resulting graph shows the communication relationship between:

```text
minimal_publisher
       │
       ▼
   /chatter
       │
       ▼
minimal_subscriber
```


##  Key ROS 2 Concepts

### Node

A **node** is an individual process that performs a specific task in a ROS 2 system.

### Publisher

The publisher sends messages to a topic.

```text
minimal_publisher → /chatter
```

### Subscriber

The subscriber receives messages from a topic.

```text
/chatter → minimal_subscriber
```

### Topic

A topic provides the communication channel through which ROS 2 nodes exchange messages.

In this project:

```text
/chatter
```

---

##  Learning Outcome

After completing this project, you should understand the basic ROS 2 communication flow:

```text
ROS 2 Workspace
      ↓
ROS 2 Package
      ↓
      Nodes
     ↙    ↘
Publisher  Subscriber
     ↓
  /chatter
     ↓
Messages
```

This provides the foundation for more advanced ROS 2 systems involving **sensors, robot control, perception pipelines, and autonomous robots**.

---

##  Possible Extensions

The basic publisher-subscriber system can be extended by:

* Publishing sensor data
* Subscribing to camera or LiDAR topics
* Publishing robot commands
* Connecting multiple publishers and subscribers
* Using custom ROS 2 messages
* Integrating the nodes with a simulated robot
* Building a perception pipeline using OpenCV

---

##  Technologies

* **ROS 2 Humble**
* **Python**
* **rclpy**
* **colcon**
* **rqt_graph**
* **Ubuntu 22.04**
* **WSL2**

---


```
```
