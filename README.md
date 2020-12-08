# LAB-3
学生教授选课

# 阅读程序
Test.java


package pack1;

public class Test {
	public static void main(String args[]) {
		CPU cpu = new CPU();
		HardDisk HD=new HardDisk();
		cpu.setSpeed(3000);
		HD.setAmount(200);
		PC pc =new PC();
		pc.setCPU(cpu);
		pc.setHardDisk(HD);
		pc.show();
		}
	}


PC.java


package pack1;

public class PC {
	CPU cpu;
	HardDisk HD;
	void setCPU(CPU cpu) {
		this.cpu = cpu;
		}
	void setHardDisk(HardDisk HD) {
		this.HD = HD;
		}
	void show(){
		System.out.println("CPU速度:"+cpu.getSpeed());
		System.out.println("硬盘容量:"+HD.getAmount());
		}
}



CPU.java


package pack1;

public class CPU {
	int speed; 
	int getSpeed() {
		return speed;
		}
	public void setSpeed(int speed) {
		this.speed = speed;
		}
	}



HardDisk.java

package pack1;

public class HardDisk {
	int amount; 
	int getAmount() {
		return amount;
		}
	public void setAmount(int amount) {
		this.amount = amount;
		}
	}
  
## 实验目的
初步了解分析系统需求，从学生选课角度了解系统中的实体及其关系，学会定义类中的属性以及方法；
掌握面向对象的类设计方法（属性、方法）；
掌握类的继承用法，通过构造方法实例化对象；
学会使用super()，用于实例化子类；
掌握使用Object根类的toString（）方法,应用在相关对象的信息输出中。

  
## 实验过程
本次实验需要确认面向对象的类设计方法，要学会根据面向的对象来设计类，然后又根据要求的对象决定属性以及构造方法，并且还要设计一个公共父类，让其余的子类继承它的属性与方法，由题目可知要设计的父类是人员，然后子类是教师和学生。另一个子类课程我只是调用人员中的一部分,最后得出结果。
  
## 核心方法
CPU类要求getSpeed()返回speed的值，要求setSpeed(int m)方法将参数m的值赋值给speed。
HardDisk类要求getAmount()返回amount的值，要求setAmount(int m)方法将参数m的值赋值给amount。
PC类要求setCPU(CPU c)将参数c的值赋值给cpu，要求setHardDisk(HardDisk h)方法将参数h的值赋值给HD，要求show()方法能显示cpu的速度和硬盘的容量。
主类 Test 的要求 
（1） main 方法中建立一个 CPU 对象 cpu，cpu 将本身的 speed 设置为 4000；
（2） main 方法中建立一个 HardDisk 对象 disk，disk 将本身的 amount 设置为 200；
（3） main 方法中建立一个 PC 对象 pc；
（4） pc 调用 setCPU(CPU c)方法，调用时实参是 cpu； 
（5） pc 调用 setHardDisk(HardDisk h)方法，调用时实参是 disk；
（6） pc 调用 show()方法。

## 实验结果
CPU速度：3000
硬盘容量：200

## 实验感想
通过这个PC机模拟程序实验我学习到了，在JAVA程序里如何确定类的关系和构造方法以及对它的赋值，也明白了主类如何引用其余的类。对如何去设定一个程序的大体框架也有了大体的理解，这次实验让我再次体会到了JAVA的面向对象的特点。通过这个PC机模拟程序实验我学习到了，在JAVA程序里如何确定类的关系和构造方法以及对它的赋值，也明白了主类如何引用其余的类。对如何去设定一个程序的大体框架也有了大体的理解，这次实验让我再次体会到了JAVA的面向对象的特点。

