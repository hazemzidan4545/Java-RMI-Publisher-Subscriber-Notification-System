# Java RMI Publisher-Subscriber Notification System

A distributed publisher-subscriber notification system built with Java RMI. Publishers send messages to named topics, subscribers choose the topics they care about, and the server routes notifications in real time.

## Features

- Central Java RMI broker.
- Publisher registration and deregistration.
- Subscriber registration and deregistration.
- Topic-based subscriptions.
- Real-time message delivery to subscribed clients.
- Message history by topic.
- Swing GUI windows for server monitoring and subscriber notifications.

## Project Structure

```text
ServerSide/
  BUEServer.java                  Main server implementation
  BUEServerGUI.java               Server monitoring GUI
  ServiceInterface.java           Server remote interface
  PublisherInterface.java         Publisher callback interface
  SubscriberInterface.java        Subscriber callback interface

ClientSide/
  PublisherApp.java               Publisher client
  SubscriberApp.java              Subscriber client
  SubscriberNotificationCenter.java
```

## Prerequisites

- Java JDK 8 or newer.
- A terminal with access to `javac`, `java`, and `rmiregistry`.

## Run

Compile:

```bash
javac -d . ServerSide/*.java ClientSide/*.java
```

Start the RMI registry:

```bash
rmiregistry 1099
```

In a separate terminal, start the server:

```bash
java ServerSide.BUEServer
```

Start one or more publishers:

```bash
java ClientSide.PublisherApp
```

Start one or more subscribers:

```bash
java ClientSide.SubscriberApp
```

## Default Topics

- New Courses
- Student Activities
- Emergency Alerts
- Campus News

## How It Works

1. Publishers connect to the RMI server and publish a message for a selected topic.
2. Subscribers connect to the RMI server and subscribe to one or more topics.
3. The server stores messages and forwards new notifications to matching subscribers.
4. Subscriber notification windows display new messages as they arrive.

## Troubleshooting

- If clients cannot connect, confirm `rmiregistry` and `BUEServer` are both running.
- If classes are not found, re-run the compile command from the repository root.
- If GUI windows do not open, run the project in an environment with desktop display support.

## Scope

This is an educational Java RMI implementation intended to demonstrate distributed publish-subscribe messaging patterns.
