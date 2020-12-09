# LAB-3
学生教授选课

# 阅读程序
Test.java


public class Teacher {
    private int id;
    private String teacherName;
private Course[] courses;
    public Teacher() {
        super();
        courses= new Course[3];
    }
    public Teacher(int id,String teacherName){
        this.id=id;
        this.teacherName=teacherName;
        courses = new Course[3];
}

    public int getId() {
        return id;
    }
    public void setId(int id) {
        this.id = id;
    }
    public String getTeacherName() {
        return teacherName;
    }
    public void setTeacherName(String teacherName) {
        this.teacherName = teacherName;
    }


}

package test;

public class Student {
	private String stuName;
    private int stuId;
    private String major;
    private Course[] courses;
    //构造函数
    public Student() {//不要忘
        super();
        courses = new Course[3];
    }
    public Student(int stuId,String stuName) {
        super();
        this.stuId=stuId;
        this.stuName=stuName;
        courses = new Course[3];
    }
    public Student(int stuId,String stuName,String major) {
        super();
        this.stuId=stuId;
        this.stuName=stuName;
        this.major = major;
        courses = new Course[3];
    }
    //修改获取属性name,id,major
    public String getStuName() {
        return stuName;
    }

    public void setStuName(String stuName) {
        this.stuName = stuName;
    }
    public int getStuId() {
        return stuId;
    }
    public void setStuId(int stuId) {
        this.stuId = stuId;
    }
    public String getMajor() {
        return major;
    }
    public void setMajor(String major) {
        this.major = major;
    }
    //学生选课；
    public boolean addCourse(Course course){
        boolean flag=false;
        if(!isSelectedCourse(course)&&isNullCourse(course)){
            for(int i=0;i<this.courses.length;i++){
                if(courses[i]==null){
                    courses[i]=course;
                    course.addStudent(this);//课程也要添加学生
                    flag=true;
                    break;
                }
            }
        }
        return flag;
    }
    //学生移除课程
    public boolean removeCourse(Course course){
        boolean flag=false;
        if(isSelectedCourse(course)){
            for(int i=0;i<this.courses.length;i++){
                if(courses[i]==course){
                    courses[i]=null;
                    course.removeStudent(this);//在课程中移除学生
                    flag=true;
                    break;
                }
            }

        }
        return flag;
    }
    //显示学生所选的课程
    public void displayCourse(){
        System.out.println("学生"+this.stuName+"所选课程有：");
        for(Course c:courses){
            if(c!=null){
                System.out.print(c.getName()+" ");
            }
        }
        System.out.println();
    }

    //子方法1：课是否被选过
    public boolean isSelectedCourse(Course course){
        boolean flag=false;
        for(Course c:courses){
            if(c==course){
                flag=true;
                break;
            }
        }
        return flag;
    }
    //子方法2：学生是否还有选修课位置
    public boolean isNullCourse(Course course){
        boolean flag=false;
        for(Course c:courses){
            if(c==null){
                flag=true;
                break;
            }
        }
        return flag;
    }


}

package test;

public class Course {
	private String courseName;
    private int courseId;
    private Teacher teacher;
    private float credit;
    private Student[] students;
    public Course(int courseId,String courseName,float credit,Teacher teacher) {
        super();
        this.courseId=courseId;
        this.courseName=courseName;
        this.credit=credit;
        this.setTeacher(teacher);
        students = new Student[30];
    }
    public Course(int courseId,String courseName,float credit) {
        super();
        this.courseId=courseId;
        this.courseName=courseName;
        this.credit=credit;
        students = new Student[30];
    }

    public Course(int courseId,String courseName) {
        super();
        this.courseId=courseId;
        this.courseName=courseName;
        students = new Student[30];
    }

    public Course() {
        super();
        students = new Student[30];
    }

    public void setId(int id){
        this.courseId=id;
    }
    public int getId(){
        return this.courseId;
    }
    public void setName(String name){
        this.courseName=name;
    }
    public String getName(){
        return this.courseName;
    }
    public void setCredit(float credit ){
        this.credit=credit;
    }
    public float getCredit(){
        return this.credit;
    }
    public Teacher getTeacher() {
        return teacher;
    }
    public void setTeacher(Teacher teacher) {
        this.teacher = teacher;
    }

    public boolean addStudent(Student stu){
        boolean flag = false;
        if(!isSelectedStudent(stu)&&isNullStudent(stu)){
            for(int i=0;i<students.length;i++){
                if(students[i]==null){
                    students[i]=stu;
                    flag=true;
                    break;
                }
            }
        }
        return flag;
    }
    
    public boolean removeStudent(Student stu){
        boolean flag=false;
        if(isSelectedStudent(stu)){
            for(int i=0;i<students.length;i++){
                if(students[i]==stu){
                    students[i]=null;
                    flag=true;
                    break;
                }
            }
        }
        return flag;
    }
   
    public void displayStudent(){
        System.out.println("Ñ¡ÔñµÄ¿Î³Ì£º"+this.courseName+"µÄÑ§ÉúÓÐ:");
        for(Student s:students){
            if(s!=null){
                System.out.print(s.getStuName()+" ");
            }
        }
        System.out.println();
    }
   
    public boolean isSelectedStudent(Student stu){
        boolean flag=false;
        for(Student s:students){
            if(s==stu){
                flag=true;
                break;
            }
        }
        return flag;
    }
   
    public boolean isNullStudent(Student stu){
        boolean flag=false;
        for(Student s:students){
            if(s==null){
                flag=true;
                break;
            }
        }
        return flag;
    }
    public static void main(String[] args) {
      
    }


}

package test;

public class ChooseCourse {
	public static void main(String[] args) {
        Student stu0 = new Student(1001,"Lily");
        Student stu1 = new Student(1002,"Eilly");
        Student stu2 = new Student(1003,"Floris");
        Student stu3 = new Student(1004,"HaHa");
        Course cour0 = new Course(001,"¸ßÊý");
        Course cour1 = new Course(002,"Ïß´ú");
        Course cour2 = new Course(003,"¸ÅÂÊÂÛ");
        stu0.addCourse(cour0);
        stu0.addCourse(cour2);
        stu0.addCourse(cour1);
        stu1.addCourse(cour2);
        stu1.addCourse(cour0);
        stu2.addCourse(cour1);
        stu3.addCourse(cour0);
        stu3.addCourse(cour1);
        stu1.removeCourse(cour2);
        stu0.displayCourse();
        cour0.removeStudent(stu1);
        cour1.displayStudent();
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
https://github.com/BiptWPC/LAB-3/raw/master/结果.PNG

## 实验感想
通过这个学生教师模拟选课系统实验我学习到了在JAVA程序里如何确定类的关系和构造方法以及对它的赋值， 本次实验我明白了系统需求和学生选课的角度，理解了如何了解系统及其关系来设计变量。知道了类中属性和方法的关系，相信通过这次实验我会根据不同题目的需求来设计掌握面向对象的设计方法。对如何去设定一个程序的大体框架也有了大体的理解，这次实验让我再次体会到了JAVA的面向对象的特点。

