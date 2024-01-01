# Chapter 6 Threads

***

## Concurrent Systems

- multi proccessor CPU can achive true multi threading, meaning that each thread can run at the same time.
- single proccessor CPU can mimic the same behaviour by sharing CPU time for all threads and the OS is responsible for scheduling and rescource allocation

***

## Creating Threads in Java code

<details>
<summary>Inheriting From Java thread Class</summary>
<br>
This Can be achived by overriding the java function from java.lang.Thread (no need to import directly as it's part of the java.lang which is imported by default)

```java 
public void run(); 
``` 
<br><br>

#### Note

Java doesn't allow multiple inheritance. <br>

#### Example Code
```java
Class ThreadA extends Thread {

    @override
    public void run()
    {
        ///code to be executed
    }

}
```
#### Note Java program execution always starts from the main function <br>

The thread can be executed from creating an object from ThreadA class then calling the function start();
<br><br>

#### Note: When Launching a thread we use the ```.start();``` method and not the ```.run();``` method this is to allow code to be ran in a parallel manner  (see following Comparison) <br><br>

<table>
    <tr>
    <th>Using .start() method</th>
    <th>Using .run() method</th>
    </tr>
    <tr>
    <th> Output: aaaaabbbbbaaaaabbbbbaaaa</th>
    <th>Output: aaaaaaaaabbbbbbbbbb</th>
    </tr>
</table>
<br>




</details>


<details>
<summary>Implement the Runnable Interface</summary>
-It is a functional interface
-Doesn't contain a start method unlike the previous example.
    -As a result we need to implement an object of the Thread class as a wrapper to call the thread from<br>

```java
ThreadA thA = new ThreadA(); // Thread a being the object of the class that implements Runnable
Thread th = new Thread(thA); //th being the wrapper object used to call ThreadA obj thA and has thA attached to it 
th.start(); 
```

##### Worth noting:
using an anonymous object is possible too in this implementation

```java
Thread th = new Thread(new ThreadA());
th.start();
```

***

</details>

## Thread States

When a thread is first created it's put in a 'New' state, As the .start() function is called the Thread moves from the 'New' state into the Ready state (no code execution starts yet), the next step is that said thread will be selected by JVM to get executed which allowes the thread to get required resources from the CPU and get to the Running state. <br>

After the Threadd is done executing the code and the run() method is completed the thread moves into the Finished state. <br><br>

#### Note: <br>
In Many cases the Thread can returned into the Ready state such as:
- The Thread is done running and moved into the Finished state which after a timeout would lead to the thread returning into the Ready state.
- yield function called that would give way to another threads having higher priority.
- Another reason is that the Thread can go into the Blocked state which would also have the same effect and has the following possiblities:
    - Waiting for a timeout.
    - Waiting for a signal to be re-activated.
    - Waiting for a Target (ex: another thread) to finish execution.

___

## Shared Data
When 2 threads try accessing the same data or attribute to do some operation many logical errors can arise due to the fact that the 2 threads are accessing 2 different versions of the same data both not having the same value. To solve this problem we can use the 'synchronized(){}' method to lock access to said attribute until a single thread is done with using the attr. <br>

#### Example of the synchronized function being used:
<br>

```java
public void run(){
synchronized(ac){
double b = ac.getBalance();
try { sleep(50); }
catch (InterruptedException e)
{ System.out.println(e); }
if(type) { ac.setBalance(b+am);
 System.out.println("Deposit, " +
"balance = "+ ac.getBalance());
} else { ac.setBalance(b+am);
System.out.println("Withdraw, " +
 "balance = "+ ac.getBalance());
}
}

```
The previous code would ensure that no logical errors would occour during code execution due to un-synchronized data.

##### Note: an entire function can be synced rather than a single attribute, this would be usefull when multiple attributes need to be synced. <br>

Example: <br>

```java
Class Account {
    public synchronized void update(double am, Boolean type){
        //code logic goes here
    }
}
class Transaction extends Thread { // Other class members
    private Account ac;
    @Override
    public void run(){ ac.update(am,type); }
}

```

## Thread Class

The thread class Has multiple attributes and methods in addition to previously mentioned ones, such as:
- start();
- isAlive();
- setPriority(int priority);
    - Priority can Range from 1 -> 10, 1 being the lowest priority and 10 being the highest.
    - The thread class has three constants (or "Macros" in c++ terms) for three levels of priority as follows:
        - public final static int MIN_PRIORITY = 1;
        - public final static int NORM_PRIORITY = 5;
        - public final static int MAX_PRIORITY = 10;
- join(); //Waits for this thread to finish execution
- sleep(int milliseconds); 
- yield(); //It Causes this thread to pause execution allowing other threads to continue running.
- interrupt();


<!--- Material done by Daniel Michel--->
<!--- https://github.com/DanielMichel305-->








