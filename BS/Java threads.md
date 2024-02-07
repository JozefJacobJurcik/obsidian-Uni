### Creating a Thread

There are two ways to create a thread.

It can be created by extending the `Thread` class and overriding its `run()` method:

```java
public class Main extends Thread {
  public void run() {
    System.out.println("This code is running in a thread");
  
```

Another way to create a thread is to implement the `Runnable` interface:

### Implement Syntax

```java
public class Main implements Runnable {
  public void run() {
    System.out.println("This code is running in a thread");
  }
}
```

### Running Threads

If the class extends the `Thread` class, the thread can be run by creating an instance of the class and call its `start()` method:

##### Extend Example

```java
public class Main extends Thread {
  public static void main(String[] args) {
    Main thread = new Main();
    thread.start();
    System.out.println("This code is outside of the thread");
  }
  public void run() {
    System.out.println("This code is running in a thread");
  }
}
```

If the class implements the `Runnable` interface, the thread can be run by passing an instance of the class to a `Thread` object's constructor and then calling the thread's `start()` method:

##### Implement Example

```java
public class Main implements Runnable {
  public static void main(String[] args) {
    Main obj = new Main();
    Thread thread = new Thread(obj);
    thread.start();
    System.out.println("This code is outside of the thread");
  }
  public void run() {
    System.out.println("This code is running in a thread");
  }
}
```

### Concurrency Problems

Because threads run at the same time as other parts of the program, there is no way to know in which order the code will run. When the threads and main program are reading and writing the same variables, the values are unpredictable. The problems that result from this are called concurrency problems.

##### Example

A code example where the value of the variable **amount** is unpredictable:

```java
public class Main extends Thread {
  public static int amount = 0;

  public static void main(String[] args) {
    Main thread = new Main();
    thread.start();
    System.out.println(amount);
    amount++;
    System.out.println(amount);
  
```

To avoid concurrency problems, it is best to share as few attributes between threads as possible. If attributes need to be shared, one possible solution is to use the `isAlive()` method of the thread to check whether the thread has finished running before using any attributes that the thread can change.

##### Example

Use `isAlive()` to prevent concurrency problems:

```java
public class Main extends Thread {
  public static int amount = 0;

  public static void main(String[] args) {
    Main thread = new Main();
    thread.start();
    // Wait for the thread to finish
    while(thread.isAlive()) {
    System.out.println("Waiting...");
  
```

### Synchronized

```java
public class TestThread extends Thread {
    String name;
    TheDemo theDemo;

    public TestThread(String name, TheDemo theDemo) {
        this.theDemo = theDemo;
        this.name = name;
        start();
    }

    @Override
    public void run() {
        theDemo.test(name);
    }

    public static class TheDemo {
        public synchronized void test(String name) {
            for (int i = 0; i < 10; i++) {
                System.out.println(name + " :: " + i);
                try {
                    Thread.sleep(500);
                } catch (Exception e) {
                    System.out.println(e.getMessage());
                }
            }
        }
    }

    public static void main(String[] args) {
        TheDemo theDemo = new TheDemo();
        new TestThread("THREAD 1", theDemo);
        new TestThread("THREAD 2", theDemo);
        new TestThread("THREAD 3", theDemo);
    }
}
   
```

Note: `synchronized` blocks the next thread's call to method test() as long as the previous thread's execution is not finished. Threads can access this method one at a time. Without `synchronized` all threads can access this method simultaneously.

When a thread calls the synchronized method 'test' of the object (here object is an instance of 'TheDemo' class) it acquires the lock of that object, any new thread cannot call ANY synchronized method of the same object as long as previous thread which had acquired the lock does not release the lock.

Similar thing happens when any static synchronized method of the class is called. The thread acquires the lock associated with the class(in this case any non static synchronized method of an instance of that class can be called by any thread because that object level lock is still available). Any other thread will not be able to call any static synchronized method of the class as long as the class level lock is not released by the thread which currently holds the lock.

**Output with synchronised**

```java
THREAD 1 :: 0
THREAD 1 :: 1
THREAD 1 :: 2
THREAD 1 :: 3
THREAD 1 :: 4
THREAD 1 :: 5
THREAD 1 :: 6
THREAD 1 :: 7
THREAD 1 :: 8
THREAD 1 :: 9
THREAD 3 :: 0
THREAD 3 :: 1
THREAD 3 :: 2
THREAD 3 :: 3
THREAD 3 :: 4
THREAD 3 :: 5
THREAD 3 :: 6
THREAD 3 :: 7
THREAD 3 :: 8
THREAD 3 :: 9
THREAD 2 :: 0
THREAD 2 :: 1
THREAD 2 :: 2
THREAD 2 :: 3
THREAD 2 :: 4
THREAD 2 :: 5
THREAD 2 :: 6
THREAD 2 :: 7
THREAD 2 :: 8
THREAD 2 :: 9
```

**Output without synchronized**

```java
THREAD 1 :: 0
THREAD 2 :: 0
THREAD 3 :: 0
THREAD 1 :: 1
THREAD 2 :: 1
THREAD 3 :: 1
THREAD 1 :: 2
THREAD 2 :: 2
THREAD 3 :: 2
THREAD 1 :: 3
THREAD 2 :: 3
THREAD 3 :: 3
THREAD 1 :: 4
THREAD 2 :: 4
THREAD 3 :: 4
THREAD 1 :: 5
THREAD 2 :: 5
THREAD 3 :: 5
THREAD 1 :: 6
THREAD 2 :: 6
THREAD 3 :: 6
THREAD 1 :: 7
THREAD 2 :: 7
THREAD 3 :: 7
THREAD 1 :: 8
THREAD 2 :: 8
THREAD 3 :: 8
THREAD 1 :: 9
THREAD 2 :: 9
THREAD 3 :: 9
```

### Wait and notify

```java

public class Data {
    private String packet;
    
    // True if receiver should wait
    // False if sender should wait
    private boolean transfer = true;
 
    public synchronized String receive() {
        while (transfer) {
            try {
                wait();
            } catch (InterruptedException e) {
                Thread.currentThread().interrupt(); 
                System.err.println("Thread Interrupted");
            }
        }
        transfer = true;
        
        String returnPacket = packet;
        notifyAll();
        return returnPacket;
    }
 
    public synchronized void send(String packet) {
        while (!transfer) {
            try { 
                wait();
            } catch (InterruptedException e) {
                Thread.currentThread().interrupt(); 
                System.err.println("Thread Interrupted");
            }
        }
        transfer = false;
        
        this.packet = packet;
        notifyAll();
    }
}
```

- The _packet_ variable denotes the data that is being transferred over the network.
- We have a _boolean_ variable _transfer_, which the _Sender_ and _Receiver_ will use for synchronization:
    - If this variable is _true_, the _Receiver_ should wait for _Sender_ to send the message.
    - If it’s _false_, _Sender_ should wait for _Receiver_ to receive the message.
- The _Sender_ uses the _send()_ method to send data to the _Receiver_:
    - If _transfer_ is _false_, we’ll wait by calling _wait()_ on this thread.
    - But when it is _true_, we toggle the status, set our message, and call _notifyAll()_ to wake up other threads to specify that a significant event has occurred and they can check if they can continue execution.
- Similarly, the _Receiver_ will use the _receive()_ method:
    - If the _transfer_ was set to _false_ by _Sender_, only then will it proceed, otherwise we’ll call _wait()_ on this thread.
    - When the condition is met, we toggle the status, notify all waiting threads to wake up, and return the data packet that was received.

