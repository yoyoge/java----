# java reflection
java反射机制总结
/**
 * 理解反射机制：
 * 1，类对象/Class对象/类的类
 * 每个java类运行时都在JVM里表现为一个class对象，
 * 获取class对象方式：
 * 1)类名.class,
 * 2)类型.getClass()
 * 3)Class.forName("类名") 最常用方式
 * 
 * 类加载器：将.class文件加载进jvm
 * Bootstrap Loader：负责加载系统类
 * ExtClassLoader：负责加载扩展类
 * APPClassLoader：负责加载应用类
 */
 
 /*
 * 各加载器的职责(了解)
 * 1)BootstrapClassLoader (jdk/jre/lib包中的jar文件)
 * 2)ExtClassLoader (jdk/jre/lib/ext包中的jar文件)
 * 3)AppClassLoader (自己写的类)
 * 
 * 类的加载器扩展：我们也可以自己定义类加载器(继承ClassLoader)，从类的加载器出发，看框架的源代码
 */
 
 class Student{
	private int age;
	private int weight;
	@Override
	public String toString() {
		return "Student [age=" + age + ", weight=" + weight + "]";
	}
}

public class TestReflect {
	public static void main(String[] args) throws Exception {
		Student s1=new Student();
		/*
		 * 获取类对象(Class对象)的3种方式
		 */
		Class<?> c1=s1.getClass();//c1	Student
		Class<?> c2=Student.class;
		Class<?> c3=Class.forName("reflect.Student");
    //三种方式获取的类对象相同
		System.out.println("c1="+c1);//class reflect.Student
		System.out.println(c2);//class reflect.Student
		System.out.println(c1==c2);//true
		System.out.println(c2==c3);//true
   }
}





