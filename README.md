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
本次实验需要确认面向对象的类设计方法，要学会根据面向的对象来设计类，然后又根据要求的对象决定属性以及构造方法，并且还要设计一个公共父类，让其余的子类继承它的属性与方法，由题目可知要设计的父类是
构造函数确认变量
构建公共父类ChooseCourse
构建子类Teacher
建立id 名字
构建子类Student
建立学科和其他变量方法
构建子类Course 

## 核心方法
student子类建立后封装自己的学生名变量，Course也被重新定义，Teacher也给定义了自己的id和名字，课程Course则独自定义了课程名，老师，信用，和学生ChooseCourse则是对前三者进行引用并将其进行引用，
主类 ChooseCourse 的要求 
（1） ChooseCourse引用三名学生和三门课程
（2） 要求设计的Student本身有着名字的属性方法
（3） 设计的Teacher也是同理
（4） Course则是重新设计自己的学生老师信用的变量，并且选课还施加了限制条件。

## 实验结果
CPU速度：3000
硬盘容量：200

## 实验感想
通过这个学生教师模拟选课系统实验我学习到了在JAVA程序里如何确定类的关系和构造方法以及对它的赋值， 本次实验我明白了系统需求和学生选课的角度，理解了如何了解系统及其关系来设计变量。知道了类中属性和方法的关系，相信通过这次实验我会根据不同题目的需求来设计掌握面向对象的设计方法。对如何去设定一个程序的大体框架也有了大体的理解，这次实验让我再次体会到了JAVA的面向对象的特点。

