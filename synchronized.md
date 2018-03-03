1.public synchronized void add(){} //锁当前对象

2.public void add(){
 
 synchronized(this)// 也是锁对象

}

3.public synchronized static void add(){} //锁当前类的class对象

4.synchronized内部代码执行完释放锁(对象锁／类锁)

5.当某个对象被锁住后，它的其他synchronized方法是不能被访问的

6.wait/notify方法使用场景

A a = new A();

public void add(){

 synchronized(a){// 锁变量
    
    a.wait();// 锁变量
 
 }

}

public void minus(){

 synchronized(a){// 锁变量
    
    a.notify();// 锁变量
 
 }

}
