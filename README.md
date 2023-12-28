# Scala-test
## 1. What will be printed out as the result of the following code execution?
```scala
val a = 1;
{
  val a = 2
  print(a)
}
print(a)
```
- [x] 21
- [ ] 11
- [ ] 22
- [ ] Compilation error  S
## 2. What will be the result of accessing tuple element?
```scala
val tuple5 = ("a", 1, 2.2, true, "five")
tuple5._2 
```
- [ ] "a"
- [x]	1
- [ ]	true
- [ ]	2.2
## 3. What will be the result of following code execution?
```scala
object Main extends App {
  def quiz = {
    val result = 5
       + 6
  }
  println(quiz)
} 
```
- [ ] 5
- [ ]	11
- [ ]	Runtime error
- [ ]	Compilation error
- [x]	6
## 4. What will be printed out as the result of the following code execution?
```scala
object Main extends App {
  val str = "one"
  val digit =
    str match {
      case "one" => 1
      case "two" => 2
      case "three" => 3
      case _ => -1
    }
  println(digit)
}
```
- [ ]	1 2 3 -1
- [ ]	-1
- [x]	1
- [ ]	Compilation error
## 5. What will be printed into the console?
```scala
val Constant = 'Q'
def tokenMe(ch: Char) = (ch: @switch) match {
  case ' ' | '\t' | '\n'  => 1
  case 'A' | 'Z' | '$'    => 2
  case '5' | Constant     => 3 
  case _                  => 4
}
println(tokenMe('5'))
```
- [x]	3. But code will compile with warnings
- [ ]	4
- [ ]	1
- [ ]	3
- [ ]	2
## 6. What is the returned type of this function:
```scala
def sayHelloRunnable(name: String) = new Runnable {
  def sayIt() = println(s"Hello, $name")
  def run() = sayIt()
}
```
- [x]	Runnable{def sayIt(): Unit}
- [ ]	Runnable
- [ ]	String
- [ ]	Compilation error
## 7. Scala's Unit roughly corresponds to which Java type?
- [x]	void
- [ ]	bool
- [ ]	get
- [ ]	null
## 8. What will be the result of the following code execution?
```scala
for (
  i1 <- 1 to 5
  if i1 % 2 == 0
  i2 <- 1 to i1
  if i2 > 2
) println(i2)
```
- [x]	Compilation error
- [ ]	3 4 5
- [ ]	3 4
- [ ]	Runtime error
- [ ]	1 2 3 4 5
## 9. What will be the result of calling method forall on empty Option?
```scala
val a = None
a.forall(_ == "text") 
```
- [ ]	false
- [x]	true
## 10. What is a generator expression in the following code?
```scala
for(i <- 1 to 10)
  println(i)
```
- [ ]	for(i <- 1 to 10)
- [x]	1 to 10
- [ ]	println(i)
- [ ]	i <- 1 to 10
## 11.
```scala
trait Quizful[T] {
 def fetchList: List[T]
}
// consumer side
someQuizful.fetchList
```
## If the List returned above is mutable, what does that say about the Quizful interface?
- [x]	if this List is produced on another thread than the consumer, one can have both visibility and atomicity problems - you can't know whether that will happen, unless you take a look at the Quizful's implementation.
- [x]	If it is described that access to this List must be synchronized, problem is - on which lock are you going to synchronize? Are you sure you'll get the locking order right? Locks are not composable.
- [x]	If this List is effectively immutable (i.e. still mutable, but not changed by Customer), you don't know if it will be signaled to other Consumers that may modify it by themselves, so you can't reason about what you can do with it.
- [ ]	None from the list
## 12. What will be the Map size in the following code?
```scala
val myMap = Map("MI" -> "Michigan", "OH" -> "Ohio", "WI" -> "Wisconsin", "MI" -> "Michigan")
myMap.size
```
- [ ]	2
- [x]	3
- [ ]	1
- [ ]	4
## 13. What will be the result of calling method exists on empty Option?
```scala
val a = None
a.exists(_ == "text")
```
- [ ]	false
- [x]	true
## 14. What will be the result of following code execution?
```scala
val myMap = Map("MI" -> "Michigan", "OH" -> "Ohio", "WI" -> "Wisconsin", "MI" -> "Meechigan")
myMap("MI")
```
- [ ]	Runtime error
- [x]	Meechigan
- [ ]	Compilation error
- [ ]	Michigan
## 15. What will be the result of applying fold to Option in the following code?
```scala
val number: Option[Int] = Some(3)
val noNumber: Option[Int] = None
val result1 = number.fold(1)(_ * 3)
val result2 = noNumber.fold(1)(_ * 3)
println(result1)
println(result2)
```
- [ ]	Some(9) None
- [ ]	3 3
- [ ]	Some(9) Some(1)
- [x]	9 1
## 16. What will be the result of comparing List with Vector, HashSet with TreeSet?
```scala
List(1, 2, 3) == Vector(1, 2, 3) // 1
HashSet(1, 2) == TreeSet(2, 1) // 2
```
- [ ]	1 - true, 2 - false
- [ ]	1 - false, 2 - true
- [ ]	1 - false, 2 - false
- [x]	1 - true, 2 - true
## 17. What will be the result of comparing Maps with the same elements in different order?
```scala
val myMap1 = Map("MI" -> "Michigan", "OH" -> "Ohio", "WI" -> "Wisconsin", "IA" -> "Iowa")
val myMap2 = Map("WI" -> "Wisconsin", "MI" -> "Michigan", "IA" -> "Iowa", "OH" -> "Ohio")
myMap1.equals(myMap2)
```
- [x]	true
- [ ]	false
## 18. What should be used instead of someMethod in the following code to get correct results?
```scala
case class Employee(
    name: String, 
    department: String, 
    manager: Option[String]
)
def lookupByName(name: String): Option[Employee] = name match {
  case "Joe" => Some(Employee("Joe", "Finances", Some("Julie")))
  case "Mary" => Some(Employee("Mary", "IT", None))
  case "Izumi" => Some(Employee("Izumi", "IT", Some("Mary")))
  case _ => None
}
def getManager(employee: Option[Employee]): Option[String] = employee.flatMap(_.manager)
getManager(lookupByName("Joe")).someMethod(Some("Mr. CEO")) == Some("Julie")
getManager(lookupByName("Mary")).someMethod(Some("Mr. CEO")) == Some("Mr. CEO")
getManager(lookupByName("Foo")).someMethod(Some("Mr. CEO")) == Some("Mr. CEO")
```
- [ ]	flatMap
- [x]	orElse
- [ ]	getOrElse
- [ ]	map
## 19. What will be the result of comparing Lists using eq function?
```scala
val a = List(1, 2, 3)
val b = List(1, 2, 3)
a eq b
```
- [x]	false
- [ ]	true
## 20. What will be the result of comparing collections?
```scala
mutable.Seq(1,2,3) == immutable.Seq(1,2,3)
```
- [x]	true
- [ ]	false
## 21. What will be the result of comparing empty lists (Nil)?
```scala
val a: List[String] = Nil
val b: List[Int] = Nil
a == Nil // 1
a eq Nil // 2
b == Nil // 3
b eq Nil // 4
a == b // 5
a eq b // 6
```
- [ ]	1, 3, 5 - true; 2, 4, 6 - false
- [ ]	Everything is false
- [ ]	1, 2, 3, 4 - true; 5, 6 - false
- [x]	Everything is true
## 22. What will be the result of applying map function to the values of type Option in the following code?
```scala
val number: Option[Int] = Some(3)
val noNumber: Option[Int] = None
val result1 = number.map(_ * 1.5)
val result2 = noNumber.map(_ * 1.5)
println(result1)
println(result2)
```
- [x]	Some(4.5) None
- [ ]	None Some(3)
- [ ]	Some(3) None
- [ ]	Some(1.5) Some(1.5)
## 23. What should be used instead of someMethod in the following code to get correct results?
```scala
case class case class Employee(name: String, department: String, manager: Option[String])
def lookupByName(name: String): Option[Employee] = name match {
  case "Joe" => Some(Employee("Joe", "Finances", Some("Julie")))
  case "Mary" => Some(Employee("Mary", "IT", None))
  case "Izumi" => Some(Employee("Izumi", "IT", Some("Mary")))
  case _ => None
}
lookupByName("Joe").someMethod(_.department != "IT") == Some(Employee("Joe", "Finances", Some("Julie")))
lookupByName("Mary").someMethod(_.department != "IT") == None
lookupByName("Foo").someMethod(_.department != "IT") == None
```
- [x]	filter
- [ ]	exists
- [ ]	forall
- [ ]	filterNot
## 24. 
```scala
case class Key(x: Int, var y: Int)
val key = Key(1,2)
val someMap = Map(key -> (1,2))
val newKey = key
newKey.y = 3  
val newMap = someMap + (newKey -> (1,3))
println(newMap(key))
```
## What will be printed into the console?
- [x]	(1,3)
- [ ]	Runtime error will occure
- [ ]	Compilation error will occur
- [ ]	(1,2)
## 25. Try to fix the loop function inside fib so that it returns the correct values for each case in a tail-recursive way. What should the missing expressions for the trivial case and the recursive call be?
```scala
def fib(n: Int): Int = {
  @annotation.tailrec
  def loop(n: Int, prev: Int, cur: Int): Int =
    if (n <= __ ) prev
    else loop(n - __, cur, prev + cur)
  loop(n, 0, 1)
}
```
- [ ]	curr, 1
- [ ]	1, 1
- [x]	0, 1
- [ ]	curr, prev
## 26. Function composing feeds the output of one function to the input of another function. Look at the implementation of compose and select the correct result of code execution
```scala
 def compose[A, B, C](f: B => C, g: A => B): A => C =
  a => f(g(a))
def f(b: Int): Int = b / 2
def g(a: Int): Int = a + 2
compose(f, g)(2)
compose(g, f)(2)
```
- [ ]	2; 2
- [ ]	3; 2
- [ ]	3; 3
- [x]	2; 3
## 27. Given the following curried function, what is the correct way to get a reference to curriedSum’s “second” function?
```scala
def curriedSum(x: Int)(y: Int) = x + y
```
- [ ]	curriedSum(1, _)
- [ ]	curriedSum(1)
- [x]	curriedSum(1)_
- [ ]	curriedSum(1)._2
## 28. Take a detailed look at implementation of isSorted function, what would be the result of applying the following anonymous function with array to it?
```scala
def isSorted[A](as: Array[A], ordering: (A, A) => Boolean): Boolean = {
 @annotation.tailrec
 def go(n: Int): Boolean =
   if (n >= as.length - 1) true
   else if (ordering(as(n), as(n + 1))) false
   else go(n + 1)
 go(0)
}
isSorted(Array(1, 3, 5, 7), (x: Int, y: Int) => x > y)
```
- [x]	true
- [ ]	false
## 29. Select all correct invocations of the given function:
```scala
def sum(x: Int, y: Int = 0) = x + y
```
- [x]	sum(5, 6)
- [x]	sum(5)
- [ ]	sum{5, 6}
- [x]	sum{5}
## 30. Take a detailed look at implementation of isSorted function, what would be the result of applying the following anonymous function with array to it?
```scala
def isSorted[A](as: Array[A], ordering: (A, A) => Boolean): Boolean = {
 @annotation.tailrec
 def go(n: Int): Boolean =
   if (n >= as.length - 1) true
   else if (ordering(as(n), as(n + 1))) false
   else go(n + 1)
 go(0)
}
isSorted(Array(7, 5, 1, 3), (x: Int, y: Int) => x < y)
```
- [x]	false
- [ ]	true
