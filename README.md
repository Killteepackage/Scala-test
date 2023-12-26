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
## 7. Scala's Unit roughly corresponds to which Java type?
- [x]	void
- [ ]	bool
- [ ]	get
- [ ]	null
