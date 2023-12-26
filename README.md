# Skala-test
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
