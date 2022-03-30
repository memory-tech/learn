#### 1、守护线程

是个服务线程，是服务其他的线程，例如最典型的垃圾回收线程，用户线程执行完后不管服务线程有没有做完都强制退出，所有守护线程

都要相应退出

#### 2、创建线程的方式

```Java
import java.util.concurrent.Callable;
import java.util.concurrent.FutureTask;

/**
 * @Author Memory
 * @Date 2022/3/29 18:31
 * @Version 1.0
 */
class Thread1 extends Thread{
    @Override
    public void run() {
        System.out.println("Thread");
    }
}
class Thread2 implements Runnable{
    @Override
    public void run() {
        System.out.println("Runnable");
    }
}
class Thread3 implements Callable{
    @Override
    public Object call() throws Exception {
        System.out.println("Callable");
        return null;
    }
}
public class Example{
    public static void main(String[] args){
        Thread1 thread1=new Thread1();
        thread1.start();

        Thread thread2=new Thread(new Thread2());
        thread2.start();

        Thread3 callable=new Thread3();
        FutureTask task=new FutureTask(callable);
        Thread thread3=new Thread(task);
        thread3.start();
    }
}
```

#### 3、runnable和callable的区别

相同点是它们都是接口，都用在多线程中都需要作为Thread的target构造Thread对象来start线程；

不同点是runnable的run方法没有返回值，而callable的call方法有返回值是一个泛型（这个泛型类型要和FutureTask 的泛型类型相对应），也可以向上抛出异常，调用FutureTask的get（）方法可以得到返回值，但会阻塞主线程

#### 4、线程的状态

创建、就绪、运行、阻塞、死亡

