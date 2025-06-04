# Utilities

A shared utilities module for internal use across multiple projects. This repository contains common helper functions, classes, and reusable logic designed to simplify development and improve code maintainability.

---

## Features

- **Thread Management**: Base classes for creating and managing threads (`ThreadBase`, `QueueThread`).
- **Observer Pattern**: Implementation of the observer pattern (`Subject`, `IObserver`).
- **Timer Functionality**: High-performance timer using file descriptors (`TimerFd`).

---

## File Structure

```
├── .gitignore         # Git ignore rules
├── LICENSE            # MIT License
├── README.md          # Project documentation
├── IObserver.h        # Observer interface
├── subject.h          # Subject class for observer pattern
├── subject.cpp        # Implementation of Subject class
├── threadBase.h       # Base class for thread management
├── threadBase.cpp     # Implementation of ThreadBase
├── QueueThread.h      # Thread with task queue
├── QueueThread.cpp    # Implementation of QueueThread
├── TimerFd.h          # Timer class using file descriptors
├── TimerFd.cpp        # Implementation of TimerFd
```

---


## Usage

### Thread Management

Use `ThreadBase` to create custom threads:

```cpp
class MyThread : public ThreadBase {
protected:
    void thread() override {
        while (m_running) {
            // Your thread logic here
        }
    }
};
```

### Observer Pattern

Attach observers to a subject:

```cpp
Subject subject;
MyObserver observer;
subject.attach(&observer);
subject.notify();
```

### Timer Functionality

Set up a timer with `TimerFd`:

```cpp
TimerFd timer;
timer.SetTimer(std::chrono::milliseconds(1000), std::chrono::milliseconds(500));
timer.Start();
```

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

---




